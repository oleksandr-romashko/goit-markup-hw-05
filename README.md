# Decorative effects and Animation

## About

This is the homework solution for the Decorative effects and Animation topics, based on the task below.

This homework covers following topics:
* background images
* vector graphics
* pseudo-elements
* positioning and animation

The solution includes only the markup and corresponding CSS styles.

The provided JS script manages the opening and closing of the modal window (described in details in the [Useful information and insights section below](#useful-information-and-insights)).

### Module objectives

* To learn basic properties for setting background, gradient and shadows.
* To create decorative effects (background, shadow, etc.) on the page.
* To distinguish between SVG and SVG-sprites and be able to dynamically change their characteristics.
* To apply pseudo-elements.
* To learn the main types of positioning and be able to determine the depth (order) of positioned elements on the page.
* To learn how to set simple transition scenarios for CSS properties.
* To analyze the necessity and advantages of using CSS animations over CSS transitions.
* To create a perspective for individual or a group of elements.

## Task

* Add markup, icons styles and decorative effects to the pages as indicated on the [Homework #4 layout](https://www.figma.com/file/Kr5Q4EVrEAqpOWko4QeEJb/Web-Studio-(Version-4.0)?type=design&node-id=297016-823&t=xehgKGCXNQoohzws-0).
* To generate an SVG sprite, use the [Icomoon service](https://icomoon.io/).
* To optimize the created SVG sprite, use [SVGOMG service](https://jakearchibald.github.io/svgomg/).
* Set up GitHub Pages and add a live page to the header of the GitHub repository.
* The solution must meet the mentor's acceptance criteria.

## Useful information and insights

* Sprites with all icons are created using [IcoMoon service](https://icomoon.io/).
* Sprites are optimized using [SVGOMG service](https://jakearchibald.github.io/svgomg/).
* Tool to unminify optimisez icons [unminify](https://unminify.com/)
* Transitions may tuned up using [cubic-bezier()](https://cubic-bezier.com/) service.
* [List of properties](https://itwiki.dev/front-end/css-reference/animation/animated_properties) that can be animated. Also [w3schools.com](https://www.w3schools.com/cssref/css_animatable.php).
* <details>
  <summary>The modal window is configured using the provided JS script</summary>
  
  Initially, the modal window and the backdrop are hidden using the `is-hidden` class on the backdrop, whose selector uses the `visibility`, `opacity`, and `pointer-events` properties. 
  If the `is-hidden` class is removed from the backdrop, the backdrop and a modal window appear.
  The appearance and hiding of the modal window is animated using a transition with an arbitrary effect, such as `scale` or `translate`, and `opacity`.

  The script for the modal window is placed in the `js/modal.js` file and is connected using `<script src="./js/modal.js"></script>` tag placed before the closing `body` tag:

  ```
  (() => {
    const refs = {
      openModalBtn: document.querySelector("[data-modal-open]"),
      closeModalBtn: document.querySelector("[data-modal-close]"),
      modal: document.querySelector("[data-modal]"),
    };
    
    refs.openModalBtn.addEventListener("click", toggleModal);
    refs.closeModalBtn.addEventListener("click", toggleModal);

    function toggleModal() {
      refs.modal.classList.toggle("is-hidden");
    }
  })();
  ```

  In order for the script to work, it is necessary to add special attributes to the markup, by which the script searches for elements, as well as the `is-hidden` class for the backdrop:
  * For the modal window opening button, add the `data-modal-open` attribute. 
  * For the modal window closing button, add the `data-modal-close` attribute. 
  * For the modal window backdrop, add the `data-modal` attribute

  Modal window should open when clicked on the `Order Service` button.
  </details>
