# JCB! Field Types

### What Are JCB Field Types?
JCB Field Types act as **blueprints for Joomla form fields**.  
Each Field Type defines the structure, rules, and properties (such as required, translatable, adjustable) of a Joomla-compatible field.  

Instead of manually building repetitive XML field definitions, Field Types allow you to define:

- **Input Types** (`text`, `list`, `radio`, etc.)
- **Field Parameters** (`required`, `label`, `description`, etc.)
- **Default Values and Validation**
- **Custom Logic and Layout Overrides**

These definitions are stored centrally and reused across all fields built in JCB.

---
### Why Use Field Types?
When you create a new Field in JCB, you start by selecting a Field Type.  
This selection **automatically inherits all the structure and metadata** you defined in the Field Type.

This templating system:

- Saves time and reduces duplication
- Keeps your form field definitions consistent
- Ensures compatibility with Joomla's XML-based field system
- Allows global updates to propagate to all child fields

---
### How Do Field Types Integrate with Joomla?
Each Field Type generates **conventional Joomla XML**, which Joomla uses to automatically render HTML forms in both admin and site interfaces.  
The entire workflow is standards-based — meaning what JCB builds, Joomla understands and renders as expected.

---
### Customization & Syncing
Field Types are version-controlled and centrally managed.

- To **update a field type** from this repository in your JCB instance, simply use the `Reset` button inside the JCB GUI of field types.
- You can also **fork this repository** and point your JCB to your fork — giving you full control and independence from upstream updates.

This design promotes **collaborative sharing** while allowing **custom autonomy**.

---
### Index of JCB Field Types


 - **Accesslevel** | [Details](src/913ed2ce-836c-48e8-97af-e482441f47df) | [Settings](src/913ed2ce-836c-48e8-97af-e482441f47df/item.json) | List of user accesslevels.
 - **Calendar** | [Details](src/6cf5a33f-cb25-4a58-bfec-7e1511896402) | [Settings](src/6cf5a33f-cb25-4a58-bfec-7e1511896402/item.json) | Text box for entry of a date.
 - **Captcha** | [Details](src/206fdad4-14d0-45f1-9c84-3d09abf48a39) | [Settings](src/206fdad4-14d0-45f1-9c84-3d09abf48a39/item.json) | Captcha robot check.
 - **Category** | [Details](src/f70346b3-2096-4f44-8b26-01ab87da7d1e) | [Settings](src/f70346b3-2096-4f44-8b26-01ab87da7d1e/item.json) | Drop down list of categories.
 - **Checkbox** | [Details](src/10066262-b6e3-4f82-941e-cbe4f61ddd6c) | [Settings](src/10066262-b6e3-4f82-941e-cbe4f61ddd6c/item.json) | A single checkbox.
 - **Checkboxes** | [Details](src/ac10859b-58da-4584-9682-36a6c2c8d04d) | [Settings](src/ac10859b-58da-4584-9682-36a6c2c8d04d/item.json) | Checkboxes that can be used for multi-select.
 - **Color** | [Details](src/7f60f198-53e7-4fe9-813f-d1b6c553680e) | [Settings](src/7f60f198-53e7-4fe9-813f-d1b6c553680e/item.json) | Color picker when clicking the input box.
 - **Combo** | [Details](src/2c8b128f-7da2-4f55-b1d7-3613f902f590) | [Settings](src/2c8b128f-7da2-4f55-b1d7-3613f902f590/item.json) | Combobox list field, allows free text.
 - **Custom** | [Details](src/dd2e1f4b-f5db-45e8-85fa-efd27bae7b6a) | [Settings](src/dd2e1f4b-f5db-45e8-85fa-efd27bae7b6a/item.json) | Custom drop down list of items entries.
 - **CustomUser** | [Details](src/a4a39f70-070f-459c-be4b-0ac103a29b9a) | [Settings](src/a4a39f70-070f-459c-be4b-0ac103a29b9a/item.json) | List of users.
 - **DynamicCheckboxes@** | [Details](src/7ed21e79-cbc5-48e3-9ed0-ca72b0f2f1a1) | [Settings](src/7ed21e79-cbc5-48e3-9ed0-ca72b0f2f1a1/item.json) | Super Power Repository Paths
 - **Editor** | [Details](src/51f288d2-6eaa-42bc-a182-a6f69b3032b8) | [Settings](src/51f288d2-6eaa-42bc-a182-a6f69b3032b8/item.json) | Editor area field.
 - **Email** | [Details](src/35948af5-9e79-4454-8dfa-682ee4fdf650) | [Settings](src/35948af5-9e79-4454-8dfa-682ee4fdf650/item.json) | Email form field type.
 - **File** | [Details](src/6da71c1e-119c-4e0d-a309-f3e52ecfa1d1) | [Settings](src/6da71c1e-119c-4e0d-a309-f3e52ecfa1d1/item.json) | Input field for files
 - **Filelist** | [Details](src/0c80df15-52c6-4647-983b-4bb4888a2edf) | [Settings](src/0c80df15-52c6-4647-983b-4bb4888a2edf/item.json) | File dropdown from directory.
 - **Folderlist** | [Details](src/d3ab2ae4-9370-4497-ae6d-dee2e0b74b7a) | [Settings](src/d3ab2ae4-9370-4497-ae6d-dee2e0b74b7a/item.json) | Folder dropdown from directory.
 - **Groupedlist** | [Details](src/088d47c0-b058-4894-b92e-dcf1b9d5a722) | [Settings](src/088d47c0-b058-4894-b92e-dcf1b9d5a722/item.json) | Dropdown list of grouped custom entries.
 - **Hidden** | [Details](src/82f1b5ca-bb9b-44d7-9a7a-9a03fb2a31dd) | [Settings](src/82f1b5ca-bb9b-44d7-9a7a-9a03fb2a31dd/item.json) | Hidden field for storing fixed values.
 - **Imagelist** | [Details](src/72680e92-2859-49c6-ad92-c2329c52f9f8) | [Settings](src/72680e92-2859-49c6-ad92-c2329c52f9f8/item.json) | Image file dropdown from directory.
 - **Integer** | [Details](src/fdbb50ea-35d2-45b2-a0bc-076fdf1544b8) | [Settings](src/fdbb50ea-35d2-45b2-a0bc-076fdf1544b8/item.json) | Dropdown of integers in a set range.
 - **List** | [Details](src/a51dfc06-1b9b-4d0a-86ba-f705bcd40d4d) | [Settings](src/a51dfc06-1b9b-4d0a-86ba-f705bcd40d4d/item.json) | Dropdown list of a custom-defined entries.
 - **Media** | [Details](src/69957007-e3d4-4976-a32b-611d02dbad71) | [Settings](src/69957007-e3d4-4976-a32b-611d02dbad71/item.json) | Select or upload media via modal.
 - **Menu** | [Details](src/6349f152-8ef5-43bd-a89b-ce18f33ac5e5) | [Settings](src/6349f152-8ef5-43bd-a89b-ce18f33ac5e5/item.json) | Dropdown list of Joomla menus.
 - **Menuitem** | [Details](src/f183b0e2-017f-48bd-8dba-d332ce1b8d9e) | [Settings](src/f183b0e2-017f-48bd-8dba-d332ce1b8d9e/item.json) | Dropdown list of items within a selected menu.
 - **Meter** | [Details](src/81668284-e572-4e17-927b-ba697fc64bd0) | [Settings](src/81668284-e572-4e17-927b-ba697fc64bd0/item.json) | Displays a value within a defined range.
 - **Modal Menu** | [Details](src/715256a4-8cc2-4d66-9d08-31e58ca5b036) | [Settings](src/715256a4-8cc2-4d66-9d08-31e58ca5b036/item.json) | Styled dropdown of menu items.
 - **ModalSelect** | [Details](src/a1cdb0a5-517c-425c-998a-333e92af3e32) | [Settings](src/a1cdb0a5-517c-425c-998a-333e92af3e32/item.json) | Modal Select to manage a database record. (J5+ only)
 - **Modulelayout** | [Details](src/7520c8f4-543d-4c7a-8e4f-e2da71c3b1cd) | [Settings](src/7520c8f4-543d-4c7a-8e4f-e2da71c3b1cd/item.json) | Dropdown of module layouts.
 - **Note** | [Details](src/f9ecacd0-8481-4157-8c71-d7aaefc2b7c3) | [Settings](src/f9ecacd0-8481-4157-8c71-d7aaefc2b7c3/item.json) | Displays custom text or headings in forms.
 - **Number** | [Details](src/5abd2b73-643b-4273-841a-787991aad968) | [Settings](src/5abd2b73-643b-4273-841a-787991aad968/item.json) | Single-line number input with step controls.
 - **Password** | [Details](src/0022598d-0ee1-44f2-aa94-c2eb47595f73) | [Settings](src/0022598d-0ee1-44f2-aa94-c2eb47595f73/item.json) | Text box for entry of a password.
 - **Plugins** | [Details](src/37fa4e1d-b7ca-4a8f-aa4b-d8085c135233) | [Settings](src/37fa4e1d-b7ca-4a8f-aa4b-d8085c135233/item.json) | Dropdown of plugins from a specified folder.
 - **Privacy@** | [Details](src/60c1d674-8bb7-4b31-97ed-ee1f16bc412a) | [Settings](src/60c1d674-8bb7-4b31-97ed-ee1f16bc412a/item.json) | Joomla privacy field display.
 - **Radio** | [Details](src/b868ed59-4208-4206-8504-95a35a74a11c) | [Settings](src/b868ed59-4208-4206-8504-95a35a74a11c/item.json) | Radio buttons for option selection.
 - **Range** | [Details](src/627d3845-7273-4f75-8e63-7b3a319a42c8) | [Settings](src/627d3845-7273-4f75-8e63-7b3a319a42c8/item.json) | Slider to select a value within a range.
 - **Repeatable** | [Details](src/05bf68d4-52f9-4705-8ae7-cba137fce0ad) | [Settings](src/05bf68d4-52f9-4705-8ae7-cba137fce0ad/item.json) | Form fields with repeatable rows of inputs.
 - **SQL** | [Details](src/d4c16f1e-fd6e-4714-90eb-f9d97edd9c32) | [Settings](src/d4c16f1e-fd6e-4714-90eb-f9d97edd9c32/item.json) | Dropdown list populated by a database query.
 - **Spacer** | [Details](src/626d0cba-a908-4a4f-a447-96d781aeaa0b) | [Settings](src/626d0cba-a908-4a4f-a447-96d781aeaa0b/item.json) | Visual divider with no stored value.
 - **Subform** | [Details](src/7139f2c8-a70a-46a6-bbe3-4eefe54ca515) | [Settings](src/7139f2c8-a70a-46a6-bbe3-4eefe54ca515/item.json) | Repeating sets of nested form fields.
 - **Tag** | [Details](src/48cba89e-8fcb-481e-a7d3-2e41773e452d) | [Settings](src/48cba89e-8fcb-481e-a7d3-2e41773e452d/item.json) | Entry point for tags (either AJAX or Nested).
 - **Tel** | [Details](src/1c6c519c-3bc8-4914-8940-3e9591b0bce6) | [Settings](src/1c6c519c-3bc8-4914-8940-3e9591b0bce6/item.json) | Input field for telephone numbers.
 - **Terms@** | [Details](src/20e88943-08db-49e6-a571-dba70cdf4cca) | [Settings](src/20e88943-08db-49e6-a571-dba70cdf4cca/item.json) | Displays Joomla terms and conditions.
 - **Text** | [Details](src/201327fe-3067-4316-a155-3fe2a52e05c0) | [Settings](src/201327fe-3067-4316-a155-3fe2a52e05c0/item.json) | Single-line text input field.
 - **Textarea** | [Details](src/76fe1250-6fa7-49e5-a0ee-f06d8d4c9f99) | [Settings](src/76fe1250-6fa7-49e5-a0ee-f06d8d4c9f99/item.json) | Multi-line text input area.
 - **Time** | [Details](src/84510e0d-bf32-48ea-b522-1bee7c83e172) | [Settings](src/84510e0d-bf32-48ea-b522-1bee7c83e172/item.json) | Time form field
 - **Timezone** | [Details](src/ed8d8cf4-cb05-49cc-95ef-4ef275f539f9) | [Settings](src/ed8d8cf4-cb05-49cc-95ef-4ef275f539f9/item.json) | Dropdown list of time zones.
 - **URL** | [Details](src/8df6e07e-2b16-43ed-a18d-2059fa44cdf1) | [Settings](src/8df6e07e-2b16-43ed-a18d-2059fa44cdf1/item.json) | Text input for a valid URL.
 - **User** | [Details](src/b0641980-5e78-42f6-972f-86aa607db23e) | [Settings](src/b0641980-5e78-42f6-972f-86aa607db23e/item.json) | Modal selector for Joomla users.
 - **Usergrouplist** | [Details](src/e2f31181-fbb3-4c3a-859d-72b6b0cff308) | [Settings](src/e2f31181-fbb3-4c3a-859d-72b6b0cff308/item.json) | Dropdown list of Joomla user groups.

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")