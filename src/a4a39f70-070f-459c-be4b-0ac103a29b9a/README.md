### JCB! Field Type
# CustomUser

> List of users.

A CustomUser fieldtype displays a filtered list of users based on selected user groups. It can exclude users already linked to items in the current view, making it useful for assigning unique users within specific contexts.

| Property | Example | Adjustable | Mandatory | Description |
|----------|---------|------------|-----------|-------------|
| type | staffusers | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) can be anything, just not the same as any other default Joomla field type. |
| name | staff | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) is the unique name of the field. |
| label | Staff | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) (translatable) is the descriptive title of the field. |
| description | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) (translatable) is text that will be shown as a tooltip when the user moves the mouse over the drop-down box. |
| class | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) is a CSS class name for the HTML form field. If omitted this will default to 'inputbox'. |
| multiple | false | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) is whether multiple items can be selected at the same time (true or false). |
| required | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field must be filled before submitting the form. |
| readonly | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field cannot be changed and will automatically inherit the default value |
| disabled | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) The field cannot be changed and will automatically inherit the default value - it will also not submit |
| default | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) |  |
| hint | select a user | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) |  |
| showon | — | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | (optional) show this field on the bases of the value in another field. https://joomla.stackexchange.com/a/17682/2166 |
| extends | user | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | The JFormField sub class that should be extended. The options are ('list','radio','checkboxes') |
| table | #__users | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The table being linked to. Must be #__users |
| component | com_users | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The name of the component where this table is found. Must be com_users |
| view | ###view### | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The single view name if the place this field is added. |
| views | ###views### | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The list view name if the place this field is added. |
| value_field | name | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The name of the text field in table linked to. |
| key_field | id | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | (mandatory) The field from the linked table to save in this table as the unique key. |
| type_php_1 | // set the groups array
		return Joomla___aeb8e463_291f_4445_9ac4_34b637c12dbd___Power::getParams('com_###component###')->get('###type###'); | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | The php for the getGroups method. |
| type_phpx_1 | [code](#code-type-phpx-1) | ![yes](https://img.shields.io/badge/yes-success?style=flat-square) | ![no](https://img.shields.io/badge/no-blue?style=flat-square) | The php for the getExcluded method. |

### <a id="code-type-phpx-1"></a>Code for `code-type-phpx-1`

```php
		// To ensure that there is only one record per user
		// Get a db connection.
		$db = Factory::getDbo();
		// Create a new query object.
		$query = $db->getQuery(true);
		// Select all records from the #__###component###_###view### table from ###CODE### column".
		$query->select($db->quoteName('###CODE###'));
		$query->from($db->quoteName('#__###component###_###view###'));
		$db->setQuery($query);
		$db->execute();
		$found = $db->getNumRows();
		if ($found)
		{
			// return all users already used
			return array_unique($db->loadColumn());
		}
		return null;
```



> Integrate, customize, and update this JCB Fieldtype with ease through JCB's flexible ecosystem.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")