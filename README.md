# Node2Know — Pug Dynamic Views

A demonstration of using **Pug** (formerly Jade) to create dynamic, data-driven views.

This demo moves beyond static templates to showcase Pug's powerful features for handling logic, variables, and flow control directly in your views.

## 🚀 Core Concepts

### 1. Buffered vs. Unbuffered Code

- **Buffered Code (`=`)**: Evaluates JavaScript and outputs the result to the HTML.
  ```pug
  h1= title
  p= "Welcome " + name
  ```
- **Unbuffered Code (`-`)**: Executes JavaScript logic without outputting anything.
  ```pug
  - const isActive = true
  - const date = new Date()
  ```

### 2. Conditionals

Pug offers a clean syntax for `if`, `else if`, and `else` logic, making it easy to show/hide content based on data.

```pug
if user.loggedIn
  h2 Welcome back!
else
  button Login
```

### 3. Iteration

Looping through arrays and objects is simplified with `each`.

```pug
ul
  each item in items
    li= item.name
```

---

## 🧭 Routes & Features

### Home (`/`)

- Demonstrates **Buffered Code**: Renders a dynamic `title` and `message` passed from the server.
- Demonstrates **Unbuffered Code**: Defines a variable inside the view to construct a sentence.

### Things Inventory (`/things`)

- Demonstrates **Iteration**: Loops through an array of "Thing" objects.
- Demonstrates **Conditionals**: Checks if the list is empty or populated.
- **Filtering**: Only displays items where `active: true`.
- **Clickable List**: Entire list items are clickable links to details.

### Thing Details (`/things/:id`)

- Demonstrates **Dynamic Routing**: Finds a specific item by ID.
- **Error Handling**: Returns a 404 if the item is not found or is inactive.
- **Navigation**: Includes a "Back to Inventory" link.

---

## 📦 Install & Run

1.  **Install Dependencies**

    ```bash
    npm install
    ```

2.  **Start Server**

    ```bash
    npm run dev
    ```

3.  **Visit**
    - [http://localhost:3000](http://localhost:3000)

---

## 📁 Project Structure

```txt
.
├── app.js               # Express Application Entry
├── routers/
│   ├── indexRouter.js   # Home route (variables)
│   ├── thingRouter.js   # Things routes (array data, filtering)
│   └── pageRouter.js    # Static page routes
├── views/
│   ├── index.pug        # Home view
│   ├── things.pug       # List view (iteration/conditionals)
│   └── thing.pug        # Details view
├── public/              # Static assets (CSS, images)
└── README.md
```

---

## License

**Node2Know-LEARN-1.0**
