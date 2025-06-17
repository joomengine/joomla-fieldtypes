### JCB! Field Type
# DynamicCheckboxes@

> Super Power Repository Paths

Dynamic Checkboxes generates a list of checkboxes dynamically based on data retrieved at runtime, such as from a database query or external source. Useful for displaying variable options that may change depending on context or configuration.

| Property | Example | Adjustable | Mandatory | Description |
|----------|---------|------------|-----------|-------------|
| type | change_this | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) can be anything, just not the same as any other default Joomla field type. You can also not use the "_" (underscore) or "-" (hyphen) in the type name, and no spaces. |
| name | dynamic_checkboxes | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) is the unique name of the field. |
| label | Dynamic Checkboxes | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) (translatable) is the descriptive title of the field. |
| description | The checkbox linked to global subform of the same name | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (translatable) is text that will be shown as a tooltip when the user moves the mouse over the drop-down box. |
| option | 1&#124;Default | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) set the options of this checkboxes. Separate options with commas and use the pipe symbol to separate value from text. |
| default | 1 | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (not translatable) is the default value. |
| required | true | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field must be filled before submitting the form. |
| showon | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) show this field on the bases of the value in another field. https://joomla.stackexchange.com/a/17682/2166 |
| onchange | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) HTML equivalent attribute (javascript use) |
| extends | checkboxes | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | Must be checkboxes |
| type_phpHEADER_1 | \JFormHelper::loadFieldClass('checkboxes');
use VDM\Joomla\Utilities\Component\Helper; | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The Header USE options |
| type_php_1 | [code](#code-type-php-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The php for the getLayoutData method. |

### <a id="code-type-php-1"></a>Code for `code-type-php-1`

```php
	/**
	 * Method to get the data to be passed to the layout for rendering.
	 *
	 * @return  array
	 *
	 * @since   3.5
	 */
	protected function getLayoutData()
	{
		$data = parent::getLayoutData();

		// True if the field has 'value' set. In other words, it has been stored, don't use the default values.
		$hasValue = (isset($this->value) && !empty($this->value));

		// If a value has been stored, use it. Otherwise, use the defaults.
		$checkedOptions = $hasValue ? $this->value : $this->checkedOptions;

		// get the form options
		$options = $this->getOptions();

		// get the component params
		$params = Helper::getParams();
		$subform  = $params->get($this->fieldname);

		// add the paths found in global settings
		if (is_array($subform) && $subform !== [])
		{
			foreach ($subform as $value)
			{
				if (isset($value->path) && strlen($value->path) > 3)
				{
					$tmp = new \stdClass;
					$tmp->value = $value->set_me;
					$tmp->text = $value->set_me;
					$tmp->checked = false;

					$options[] = $tmp;
				}
			}
		}

		$extraData = array(
			'checkedOptions' => is_array($checkedOptions) ? $checkedOptions : explode(',', (string) $checkedOptions),
			'hasValue'       => $hasValue,
			'options'        => $options
		);

		return array_merge($data, $extraData);
	}
```



> Integrate, customize, and update this JCB Fieldtype with ease through JCB's flexible ecosystem.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")