<img src="Pocket Dex/static/Frontpage.png" style="height: auto; width: auto" />
<img src="Pocket Dex/static/modal.png" style="height: auto; width: auto" />

# Pokédex Deep-Dive Project Bit-Academy

Welcome to our Svelte app! This project was built using the Svelte Kit framework & Tailwind CSS.

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Make sure you have the following tools installed on your machine:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) (Node Package Manager)

### Installing

1. Clone the repository:

```bash
git clone https://github.com/FabianvanUnen/FabianvanUnen.github.io
```

2. Navigate to the project directory:

```bash
cd Pocket_Dex
```

3. Install the dependencies:

```bash
npm install
```

### Running the App

Now that the dependencies are installed, you can run the app locally. Execute the following command:

```bash
npm run dev
```

This will start the development server. Open your browser and navigate to [http://localhost:5173](http://localhost:5173) to view the app.

If you want to open the dev server immediately:

```bash
npm run dev -- --open
```

### Project Structure

Here's a quick overview of the project structure:

- `src/` - Contains the source code of the Svelte app.

Feel free to explore and modify the code to suit your needs.

## Navigating the App

All Pokémon and its details are loaded using [A custom-tailored pokémon api](https://github.com/Lythical1/lythical1.github.io/tree/main/public/api), by [Lythical](https://github.com/Lythical1)'s team
with the exception of sprites due to a memory leak. For sprites, the infamous PokéAPI is used.

This app consists out of a few svelte components all connected to one `+page.svelte`

> There is a total of 1017 pokémon on this app loaded using this API, not all of the api's data is utilised in this app.

To view details on a pokémon, click on their little box and there should be a modal pop-up detailing and limited to:

- A pokémon's base experience;
- Their general order on the pokédex;
- Their type(s);
- A list of all learnable moves.

To search for a pokémon you can use the search bar on the top right of the site. You can also specifically look for pokémon selected from a specific type using the dropdown menu next to the search bar.
