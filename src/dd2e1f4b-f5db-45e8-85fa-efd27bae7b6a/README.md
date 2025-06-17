### JCB! Field Type
# Custom

> Custom drop down list of items entries.

The list form field type provides a drop down list or a list box of other current component table entries. If the field has a saved value this is selected when the page is first loaded. If not, the default value (if any) is selected.

| Property | Example | Adjustable | Mandatory | Description |
|----------|---------|------------|-----------|-------------|
| type | subjects | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) can be anything, just not the same as any other default Joomla field type. You can also not use the "_" (underscore) or "-" (hyphen) in the type name, and no spaces. |
| name | subject | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) is the unique name of the field. |
| label | Select a Subject | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) (translatable) is the descriptive title of the field. |
| description | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (translatable) is text that will be shown as a tooltip when the user moves the mouse over the drop-down box. |
| message | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (translatable) is text that will be shown as error on validation. |
| class | list_class | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) is a CSS class name for the HTML form field. If omitted this will default to 'inputbox'. |
| layout | joomla.form.field.list-fancy-select | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) New layout field added in Joomla 4 |
| multiple | false | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) is whether multiple items can be selected at the same time (true or false). |
| default | 0 | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (not translatable) is the default value. |
| required | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field must be filled before submitting the form. |
| validate | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The validation method for the form field.  This value will determine which method is used to validate the value for a field. |
| readonly | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field cannot be changed and will automatically inherit the default value |
| disabled | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field cannot be changed and will automatically inherit the default value - it will also not submit |
| showon | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) show this field on the bases of the value in another field. https://joomla.stackexchange.com/a/17682/2166 |
| onchange | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) HTML equivalent attribute (javascript use) |
| extends | list | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The JFormField sub class that should be extended. The options are ('list','radio','checkboxes') |
| button | true | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) to add new button next to field in edit view |
| table | #__###component###_subject | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The table being linked to. The ###TABLE### placeholder holds the table in the php. |
| component | com_###component### | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The name of the component where this table is found. Must be com_users |
| entity | ###view### | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The area/entity this custom field is loaded. This value can be used in the field custom code. |
| view | subject | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The single view name if the place this field is added. |
| views | subjects | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The list view name if the place this field is added. |
| value_field | name | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The name of the text field in table linked to. The ###TEXT### placeholder holds the value_field in the php. |
| key_field | id | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The field from the linked table to save in this table as the unique key. The ###ID### placeholder holds the key_field in the php. |
| prime_php | 1 | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | This field makes sure that the PHP used here is used to build the field type, and other are custom fields with the same field type are ignored. So to avoid that they over write the PHP added here. You should only have one prime per/type. To disable remove the field or set to 0 |
| type_php_1 | [code](#code-type-php-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | The php for the getOptions method. |

### <a id="code-type-php-1"></a>Code for `code-type-php-1`

```php
// Get the user object.
		$user = Factory::getUser();
		// Get the databse object.
		$db = Factory::getDBO();
		$query = $db->getQuery(true);
		$query->select($db->quoteName(array('a.###ID###','a.###TEXT###'),array('###ID###','###CODE_TEXT###')));
		$query->from($db->quoteName('###TABLE###', 'a'));
		$query->where($db->quoteName('a.published') . ' = 1');
		$query->order('a.###TEXT### ASC');
		// Implement View Level Access (if set in table)
		if (!$user->authorise('core.options', '[[[com_component]]]'))
		{
			$columns = $db->getTableColumns('###TABLE###');
			if(isset($columns['access']))
			{
				$groups = implode(',', $user->getAuthorisedViewLevels());
				$query->where('a.access IN (' . $groups . ')');
			}
		}
		$db->setQuery((string)$query);
		$items = $db->loadObjectList();
		$options = [];
		if ($items)
		{
			if ($this->multiple === false)
			{
				$options[] = Html::_('select.option', '', Text::_('Select an option'));
			}
			foreach($items as $item)
			{
				$options[] = Html::_('select.option', $item->###ID###, $item->###CODE_TEXT###);
			}
		}
		return $options;
```



> Integrate, customize, and update this JCB Fieldtype with ease through JCB's flexible ecosystem.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")