### JCB! Field Type
# Privacy@

> Joomla privacy field display.

The privacy field type in Joomla is a specialized custom form field introduced to assist extensions in handling privacy-related features; most notably, export and deletion requests in compliance with privacy regulations like the GDPR (General Data Protection Regulation).

| Property | Example | Adjustable | Mandatory | Description |
|----------|---------|------------|-----------|-------------|
| type | privacy | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) can be anything, just not the same as any other default Joomla field type. You can also not use the "_" (underscore) or "-" (hyphen) in the type name, and no spaces. |
| name | privacy | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) is the unique name of the field. |
| label | Privacy Policy | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) (translatable) is the descriptive title of the field. |
| description | Read the full privacy policy. | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (translatable) is text that will be shown as a tooltip when the user moves the mouse over the drop-down box. |
| filter | integer | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) is a CSS class name for the HTML form field. If omitted this will default to 'inputbox'. |
| option | 1&#124;I agree,0&#124;No | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) set the options of this radio. Separate options with commas and use the pipe symbol to separate value from text. |
| default | 0 | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (not translatable) is the default value. |
| required | true | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field must be filled before submitting the form. |
| showon | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) show this field on the bases of the value in another field. https://joomla.stackexchange.com/a/17682/2166 |
| onchange | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) HTML equivalent attribute (javascript use) |
| extends | radio | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | Must be radio |
| type_phpHEADER_1 | use Joomla\CMS\Factory;
use Joomla\CMS\Language\Text; | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The Header USE options |
| type_php_1 | [code](#code-type-php-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The php for the getInput method. |
| type_phpa_1 | [code](#code-type-phpa-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The php for the getLabel method. |
| type_phpb_1 | [code](#code-type-phpb-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The php for the getLayoutData method. |

### <a id="code-type-php-1"></a>Code for `code-type-php-1`

```php
	/**
	 * Method to get the field input markup.
	 *
	 * @return  string   The field input markup.
	 *
	 * @since   3.9.0
	 */
	protected function getInput()
	{
		// Display the message before the field
		echo $this->getRenderer('plugins.system.privacyconsent.message')->render($this->getLayoutData());

		return parent::getInput();
	}
```

### <a id="code-type-phpa-1"></a>Code for `code-type-phpa-1`

```php
	/**
	 * Method to get the field label markup.
	 *
	 * @return  string  The field label markup.
	 *
	 * @since   3.9.0
	 */
	protected function getLabel()
	{
		if ($this->hidden)
		{
			return '';
		}

		return $this->getRenderer('plugins.system.privacyconsent.label')->render($this->getLayoutData());

	}
```

### <a id="code-type-phpb-1"></a>Code for `code-type-phpb-1`

```php
	/**
	 * Method to get the data to be passed to the layout for rendering.
	 *
	 * @return  array
	 *
	 * @since   3.9.4
	 */
	protected function getLayoutData()
	{
		$data = parent::getLayoutData();

		$article = false;
		$privacyArticle = $this->element['article'] > 0 ? (int) $this->element['article'] : 0;

		if ($privacyArticle && Factory::getApplication()->isClient('site'))
		{
			$db    = Factory::getDbo();
			$query = $db->getQuery(true)
				->select($db->quoteName(array('id', 'alias', 'catid', 'language')))
				->from($db->quoteName('#__content'))
				->where($db->quoteName('id') . ' = ' . (int) $privacyArticle);
			$db->setQuery($query);
			$article = $db->loadObject();

			JLoader::register('ContentHelperRoute', JPATH_BASE . '/components/com_content/helpers/route.php');

			$slug = $article->alias ? ($article->id . ':' . $article->alias) : $article->id;
			$article->link  = ContentHelperRoute::getArticleRoute($slug, $article->catid, $article->language);
		}

		$extraData = array(
			'privacynote' => !empty($this->element['note']) ? $this->element['note'] : Text::_('By signing up to this web site and agreeing to the Privacy Policy you agree to this web site storing your information.'),
			'options' => $this->getOptions(),
			'value'   => (string) $this->value,
			'translateLabel' => $this->translateLabel,
			'translateDescription' => $this->translateDescription,
			'translateHint' => $this->translateHint,
			'privacyArticle' => $privacyArticle,
			'article' => $article,
		);

		return array_merge($data, $extraData);
	}
```



> Integrate, customize, and update this JCB Fieldtype with ease through JCB's flexible ecosystem.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")