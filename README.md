# easyMenu
Bootstrap Navbar only with JQuery

## Getting Started
This is a way to create a Navbar only using JQuery.

### Prerequisites
* JQuery
* Bootstrap

### Installing

First, you need to put the JQuery and the Bootstrap references on the head of your HTML.

Then you need to create a div tag, like this:

```
<div class="testNav"></div>
```
Then, create a javascript file, and reference it in your html head too, under the other references,
and call your div with the easyMenu method.
```
$('.testNav').easyMenu();
```
This will show you a message on you page, like this:
```
This is your blank Navbar.
```
And maybe you said, thats all?, but this is only the beginning.

This plugin has a main object to configure all the Nav, this object has other objects inside to tell the Nav what to do.

This are all the objects inside the easyMenu method:

| Command | Description |
| --- | --- |
| options | This is the main object. |
| separator | In this variable you specify the main character you will use to separate a text. |
| search_button | Is a boolean variable that says if you going to add a search button on your Navbar or not. |
| logo | This is an object that specify the logo that you are going to use, this object contain two variables ```haslogo``` and ```src```. |
| logo > haslogo | This variable is declared inside the logo object, is a boolean that specify if your Navbar is going to have a logo or not. |
| logo > src | This variable is declared inside the logo object, is a string that contains the route of your logo.  |
| tittle | This is an object that contains the tittle variables of your Navbar, this object contain two variables ```hastittle``` and ```text```.  |
| tittle > hastittle | This is a variable inside the tittle object, is a boolean variable that specify if the Navbar is going to have tittle or not.   |
| tittle > text | This is a variable inside the tittle object, is a string variable that specify the tittle text. |
| main | This is an object that contains the name of the main elements on the menu, this object contains a string variable called ```text```.  |
| main > text | This variable has the main elements on the menu, you need to put the elements separate by your ```text```, for example, if your separator is ```;``` you need to put your elements like this ```Element1;Element2;Element3,Element4```.|
| childs | This object contains the attributes of the elements on your Navbar. |
| childs > data_childs | This object contains the attributes of the elements on your Navbar, contains an object that have four variables, ```type, objetive, text``` and ```value``` .|
| childs > data_childs > navbar element name | This object has the individually variables for each element. |
| childs > data_childs > navbar element name > type | This variable is a string, that specify if the elemen is going to be a link or a dropdown. |
| childs > data_childs > navbar element name > objetive | This variable is a string, that specify which element has this configuration. |
| childs > data_childs > navbar element name > text | This is a variable used only if the element type is a dropdown, this specify the child names of the element, you need to put the names separated by your separator. |
| childs > data_childs > navbar element name > value | This specify the url of the element, in case that the element is a dropdown, you need to put the urls separated by your separator and need to match to the names specified. |
| style | This is an object to apply styles to your Navbar. |
| style > iscustom | This variable specify if your style is custom or not, this value is a boolean. |
| style > theme | If the iscustom variable is false, you can choose a theme for your Navbar. |
| style > menu |  If the iscustom variable is true, this object has the menu style options, that you can set to your main elements on the Navbar. |
| style > menu > background_color | This variable sets a background color to your Navbar. |
| style > menu > textcolor | This variable sets a font color on your main Navbar elements. |
| style > menu > fontsize | This variable sets a font size on your main Navbar elements. |
| style > menu > fontweight | This variable sets a font weight on your main Navbar elements. |
| style > submenu | If the iscustom variable is true, this object has the submenu style options, that you can set to your child elemnts on the Navbar | 
| style > submenu > background_color | This variable sets a background color to the child elements of your Navbar. |
| style > submenu > textcolor | This variable sets a font color on your child Navbar elements. |
| style > submenu > fontsize | This variable sets a font size on your child Navbar elements. |
| style > submenu > fontweight | This variable sets a font weight on your child Navbar elements. |
| style > submenu > item_active_background_color | This variable sets a background color to the child elements of your Navbar when this is focused. |
| style > tittle > background_color | This variable sets a background color to the tittle of your Navbar. |
| style > tittle > textcolor | This variable sets a font color to your Navbar tittle. |
| style > tittle > fontsize | This variable sets a font size to your Navbar tittle. |
| style > tittle > fontweight | This variable sets a font weight to your Navbar tittle. |
| style > search | If the iscustom variable is true, this object has the search element style options. |
| style > search > btn | This element has the search button style options. |
| style > search > btn > background_color | This variable sets a background color to the search button. |
| style > search > btn > textcolor | This variable sets a font color to your child search button. |
| style > search > btn > fontsize | This variable sets a font size to your search button. |
| style > search > btn > fontweight | This variable sets a font weight to your search button. |
| style > search > btn > border | This variable sets a border to your search button. |
| style > search > btn > border_radius | This variable sets a border radius to your search button. |
| style > search > input | This element has the search input style options. |
| style > search > input > background_color | This variable sets a background color to the search input. |
| style > search > input > textcolor | This variable sets a font color to your child search input. |
| style > search > input > fontsize | This variable sets a font size to your search input. |
| style > search > input > fontweight | This variable sets a font weight to your search input. |
| style > search > input > border | This variable sets a border to your search input. |
| style > search > input > border_radius | This variable sets a border radius to your search input. |


## Creating a standard navbar

This is the way to create a standard navbar with four elements, two dropdowns and two links, this navbar has a logo and a tittle:
```javascript
$('.testNav').easyMenu({
    options: {
        separator: ";",
        search_button: true,
        logo: {
            haslogo: true,
            src: 'https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-solid.svg'
        },
        tittle: {
            hastittle: true,
            text: "easyMenu"
        },
        main: {                                
            text: "Main1;Main2;Main3;Main4"
        },
        childs: {
            data_childs: {
                "Main1": {
                    type: "dropdown",
                    objetive:"Main1",
                    text: "Child1;Child2",
                    value: "http://child1.com/;http://child2.com/"
                },
                "Main2": {
                    type: "dropdown",
                    objetive:"Main2",
                    text: "Child3;Child4",
                    value: "http://child3.com/;http://child4.com/"
                },
                "Main3": {
                    type: "link",
                    objetive:"Main3",
                    value: "http://main5.com"
                },                                    
                "Main4": {
                    type: "link",
                    objetive:"Main4",
                    value: "http://main6.com"
                }
            }
        }
    }
});
```
Remember that the number of the main elements that you put on the main object has to be the same on the child object, also the same name and the same objetive, to make a reference from the main to the child.

### Styling the navbar

This plugin has a style object, to apply themes to your navbar or if you want to customize your theme, you can do it too, like this:


```javascript
$('.testNav').easyMenu({
    options: {
        separator: ";",
        search_button: true,
        logo: {
            haslogo: true,
            src: 'https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-solid.svg'
        },
        tittle: {
            hastittle: true,
            text: "easyMenu"
        },
        main: {                                
            text: "Main1;Main2;Main3;Main4"
        },
        childs: {
            data_childs: {
                "Main1": {
                    type: "dropdown",
                    objetive:"Main1",
                    text: "Child1;Child2",
                    value: "http://child1.com/;http://child2.com/"
                },
                "Main2": {
                    type: "dropdown",
                    objetive:"Main2",
                    text: "Child3;Child4",
                    value: "http://child3.com/;http://child4.com/"
                },
                "Main3": {
                    type: "link",
                    objetive:"Main3",
                    value: "http://main5.com"
                },                                    
                "Main4": {
                    type: "link",
                    objetive:"Main4",
                    value: "http://main6.com"
                }
            }
        },
        style: {
            iscustom: false,
            theme: "dark"
        }
    }
});
```
With the style object you can set a theme for your navbar, there are three theme options(for now) that you can set, this are ```dark, blue``` and the default, this default theme will be set if you set the theme variable empty for example: ```theme: ""```, or simply if you don't create the style object.

### Custom styling 

This navbar has a custom styling, you only need to set the ```iscustom``` variable to true and then apply your configuration, for example: 

```javascript
$('.testNav').easyMenu({
    options: {
        separator: ";",
        search_button: true,
        logo: {
            haslogo: true,
            src: 'https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-solid.svg'
        },
        tittle: {
            hastittle: true,
            text: "easyMenu"
        },
        main: {                                
            text: "Main1;Main2;Main3;Main4"
        },
        childs: {
            data_childs: {
                "Main1": {
                    type: "dropdown",
                    objetive:"Main1",
                    text: "Child1;Child2",
                    value: "http://child1.com/;http://child2.com/"
                },
                "Main2": {
                    type: "dropdown",
                    objetive:"Main2",
                    text: "Child3;Child4",
                    value: "http://child3.com/;http://child4.com/"
                },
                "Main3": {
                    type: "link",
                    objetive:"Main3",
                    value: "http://main5.com"
                },                                    
                "Main4": {
                    type: "link",
                    objetive:"Main4",
                    value: "http://main6.com"
                }
            }
        },
        style: {
          iscustom: true,
          menu: {                                    
              background_color: "#000000",
              textcolor: "#FFFFFF",
              fontsize: "16px",
              fontweight: "bold"
          },
          submenu: {
              background_color: "#000000",
              textcolor: "#007bff",
              fontsize: "18px",
              fontweight: "bold",
              item_active_background_color: "#000000"
          },
          tittle: {
              background_color: "#000000",
              textcolor: "red",
              fontsize: "18px",
              fontweight: "bold"
          },
          search: {
              btn: {
                  fontsize:"16px",
                  textcolor: "#007bff",
                  background_color: "#000000",
                  fontweight: "bold",
                  border: "1px solid #ced4da",
                  border_radius: ".25rem"                                  
              },
              input: {
                  fontsize:"16px",
                  textcolor: "#007bff",
                  background_color: "#000000",
                  fontweight: "bold",
                  border: "1px solid #ced4da",
                  border_radius: ".25rem"
              }
          }
       }
    }
});
```
You need to put the element styles individually, first the main elements, then the childs and then the tittle and the search element, remember that this configurations are optional, you can only set a configuration to your main elements and set the other elements by default, is your choice.

## Deployment
This is a complete example of the navbar working, you only need to set the jquery and bootstrap cdn on your head, and then put the easyMenu.js.

```html
<html>
    <head>
    <script src="components/jquery/jquery-3.4.1.min.js"></script>
    <link rel="stylesheet" href="components/bootstrap/css/bootstrap.min.css">
    <script src="components/bootstrap/js/bootstrap.min.js"></script>
    <script src="components/easymenu/easyMenu.min.js"></script>
    <script>
    $(document).ready(function() {
        $('.testNav').easyMenu({
            options: {
                separator: ";",
                search_button: true,
                logo: {
                    haslogo: true,
                    src: 'https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-solid.svg'
                },
                tittle: {
                    hastittle: true,
                    text: "easyMenu"
                },
                main: {                                
                    text: "Main1;Main2;Main3;Main4"
                },
                childs: {
                    data_childs: {
                        "Main1": {
                            type: "dropdown",
                            objetive:"Main1",
                            text: "Child1;Child2",
                            value: "http://child1.com/;http://child2.com/"
                        },
                        "Main2": {
                            type: "dropdown",
                            objetive:"Main2",
                            text: "Child3;Child4",
                            value: "http://child3.com/;http://child4.com/"
                        },
                        "Main3": {
                            type: "link",
                            objetive:"Main3",
                            value: "http://main5.com"
                        },                                    
                        "Main4": {
                            type: "link",
                            objetive:"Main4",
                            value: "http://main6.com"
                        }
                    }
                },
                style: {
                iscustom: true,
                menu: {                                    
                    background_color: "#000000",
                    textcolor: "#FFFFFF",
                    fontsize: "16px",
                    fontweight: "bold"
                },
                submenu: {
                    background_color: "#000000",
                    textcolor: "#007bff",
                    fontsize: "18px",
                    fontweight: "bold",
                    item_active_background_color: "#000000"
                },
                tittle: {
                    background_color: "#000000",
                    textcolor: "red",
                    fontsize: "18px",
                    fontweight: "bold"
                },
                search: {
                    btn: {
                        fontsize:"16px",
                        textcolor: "#007bff",
                        background_color: "#000000",
                        fontweight: "bold",
                        border: "1px solid #ced4da",
                        border_radius: ".25rem"                                  
                    },
                    input: {
                        fontsize:"16px",
                        textcolor: "#007bff",
                        background_color: "#000000",
                        fontweight: "bold",
                        border: "1px solid #ced4da",
                        border_radius: ".25rem"
                    }
                }
            }
            }
        });
    });
    </script>
    </head>
    <body>
          <div class="testNav"></div>
    </body>
</html>
```

## Built With

* [JQuery](https://jquery.com/) - The web framework used
* [Bootstrap](https://getbootstrap.com/docs/4.3/components/navbar/) - The Bootstrap Navbar

## Contributing

If you detect any problem, please let me know, any comments will be welcome.

## Versioning

See the [tags on this repository](https://github.com/Mantixd/easyMenu/tags). 

## Authors

* **Ricardo Pérez** - *Initial work* - [Mantixd](https://github.com/Mantixd)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

