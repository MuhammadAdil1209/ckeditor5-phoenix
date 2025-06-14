# CKEditor 5 for Phoenix

![CKEditor 5](https://img.shields.io/badge/CKEditor%205-Integration-blue?style=flat-square) ![Elixir](https://img.shields.io/badge/Elixir-Framework-green?style=flat-square) ![Phoenix](https://img.shields.io/badge/Phoenix-Framework-orange?style=flat-square)

Welcome to the **CKEditor 5 for Phoenix** repository! This project aims to provide a smooth WYSIWYG integration for Elixir applications. Whether you're using LiveView or traditional forms, this library is designed to fit seamlessly into your workflow. 

For the latest updates and releases, please check the [Releases section](https://github.com/MuhammadAdil1209/ckeditor5-phoenix/releases).

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Easy Setup**: Quickly integrate CKEditor 5 into your Elixir apps with minimal configuration.
- **Custom Builds**: Tailor CKEditor to your needs by creating custom builds that include only the features you require.
- **Dynamic Loading**: Load the editor dynamically based on user interactions, enhancing performance and user experience.
- **Localization**: Support multiple languages and locales to cater to a global audience.
- **Plug-and-Play Modules**: Use ready-made modules to extend functionality without heavy lifting.
- **JavaScript Hooks**: Easily add JavaScript hooks for additional interactivity.
- **Full Customization Support**: Modify the editor's appearance and behavior to match your application's style.

## Installation

To get started with CKEditor 5 for Phoenix, follow these steps:

1. Add the dependency to your `mix.exs` file:

   ```elixir
   defp deps do
     [
       {:ckeditor5_phoenix, "~> 0.1.0"}
     ]
   end
   ```

2. Run the following command to install the dependency:

   ```bash
   mix deps.get
   ```

3. Include the necessary JavaScript and CSS files in your application layout. You can find the files in the `priv/static` directory after installation.

4. Run your Phoenix server:

   ```bash
   mix phx.server
   ```

5. Open your browser and navigate to `http://localhost:4000`. You should see CKEditor 5 integrated into your application.

## Usage

To use CKEditor 5 in your forms, you can simply add the following code to your template:

```elixir
<%= form_for @changeset, @action, fn f -> %>
  <div>
    <%= text_area f, :content, class: "ckeditor" %>
  </div>
<% end %>
```

Ensure you include the appropriate JavaScript to initialize the editor:

```javascript
document.addEventListener('DOMContentLoaded', function() {
  ClassicEditor
    .create(document.querySelector('.ckeditor'))
    .catch(error => {
      console.error(error);
    });
});
```

## Customization

CKEditor 5 is highly customizable. You can modify its configuration according to your needs. Here are some common customizations:

### Toolbar Configuration

You can customize the toolbar by specifying which buttons to include:

```javascript
ClassicEditor
  .create(document.querySelector('.ckeditor'), {
    toolbar: ['bold', 'italic', 'link', 'bulletedList', 'numberedList']
  })
  .catch(error => {
    console.error(error);
  });
```

### Language Support

To change the language of the editor, you can specify the language in the configuration:

```javascript
ClassicEditor
  .create(document.querySelector('.ckeditor'), {
    language: 'fr' // Change 'fr' to your desired language code
  })
  .catch(error => {
    console.error(error);
  });
```

### Plugins

CKEditor 5 supports a variety of plugins. You can include them in your custom build or load them dynamically. For example, to add a specific plugin:

```javascript
ClassicEditor
  .create(document.querySelector('.ckeditor'), {
    extraPlugins: ['autolink'] // Add any other plugins you need
  })
  .catch(error => {
    console.error(error);
  });
```

## Contributing

We welcome contributions! To contribute to CKEditor 5 for Phoenix, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your changes to your fork.
5. Open a pull request.

Please ensure your code follows the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Conclusion

CKEditor 5 for Phoenix provides a powerful and flexible solution for integrating rich text editing capabilities into your Elixir applications. With easy setup, full customization support, and a focus on performance, it meets the needs of both developers and users alike.

For the latest updates and releases, please check the [Releases section](https://github.com/MuhammadAdil1209/ckeditor5-phoenix/releases).