# SelectBoxComponent

<img src="https://raw.githubusercontent.com/arifuzzaman-tanin/Blazor-Searchable-SelectBox/main/animated%20selectbox.png" />


## Overview

The `SelectBoxComponent` is a reusable Blazor component designed to provide a flexible and customizable dropdown select box for use in web applications. It allows users to select from a list of predefined items and provides search functionality for easy item navigation.

## Usage

### Installation

To use the `SelectBoxComponent` in your Blazor application, follow these steps:

1. Add the component to your project or reference the existing code.

2. Use the component in your Blazor page or component by including the `<SelectBoxComponent>` tag and providing the necessary parameters.

### Example

```html
<SelectBoxComponent Items="roles" ValueChangeEvent="(e) => OnChangeHandler(e)" SelectedId="5" />
<p>Value from Child: @selectBoxObject?.Text</p>
```

### Parameters

- **Items**: IEnumerable<SelectBox> (Required) - The list of items to populate the dropdown.

- **ValueChangeEvent**: EventCallback<SelectBox> (Optional) - A callback function triggered when an item is selected.

- **SelectedId**: string (Optional) - The ID of the initially selected item.

- **SelectBoxClasses**: string (Optional) - Additional CSS classes for styling the select box.

- **SearchFieldClasses**: string (Optional) - Additional CSS classes for styling the search input field.

- **OptionItemClasses**: string (Optional) - Additional CSS classes for styling the individual option items.

### Features

- **Search Functionality**: Users can search for items in the dropdown, making it easy to locate specific options.

- **Custom Styling**: Customize the appearance of the select box, search input, and option items by providing CSS classes.

- **Event Handling**: Respond to item selection by handling the `ValueChangeEvent`.

## Styling

The component provides default styling, but you can customize it by providing your own CSS classes. Below are the key styles that can be modified:

- **Dropdown Container**: `.dropdown-select-65`

- **Search Input**: `.input-search-select-65`

- **List Item Hover**: `.list-group-item:hover`

## Code Optimization

The component's code has been optimized for performance and readability. Some key optimizations include:

- Efficient item filtering using LINQ.

- Minimized redundant code in the `SetActiveClassValue` method.

- Proper handling of asynchronous operations.

## Example Implementation

The provided `HomeComponent` demonstrates how to use the `SelectBoxComponent` with a list of roles. Customize the roles based on your application's needs.

```csharp
@code{
    private IEnumerable<SelectBox> roles;
    private SelectBox selectBoxObject;

    public void OnChangeHandler(SelectBox passedObject)
    {
        selectBoxObject = passedObject;
    }

    protected override async Task OnInitializedAsync()
    {
        roles = new List<SelectBox>
            {
                new SelectBox
                {
                    Id = "3",
                    Text = "Developer"
                },
                new SelectBox
                {
                    Id = "4",
                    Text = "Manager"
                },
                new SelectBox
                {
                    Id = "5",
                    Text = "Tester"
                },
                new SelectBox
                {
                    Id = "6",
                    Text = "Designer"
                },
                new SelectBox
                {
                    Id = "7",
                    Text = "Analyst"
                }
            };

        await base.OnInitializedAsync();
    }
}
```

## Contributors

- [Md Arifuzzaman Tanin]

## License

This project is licensed under the MIT License. Feel free to modify and use it in your projects.

---

Feel free to add more details, such as additional features, configuration options, or any other relevant information based on the specifics of your component and your project's needs. Additionally, include a proper license file and credit contributors appropriately.