<template>
  <header>
	  <a href="/" class="title">Fyr0s</a>
	  <nav>
	  </nav>
  </header>
</template>

<style>
header {
	padding: 15px 30px;
	background-color: #0f1729;
	display: flex;
	justify-content: space-between;
	align-items: center;
	box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.1);
}

header .title {
	color: #BAE1F2;
	font-size: 24px;
	font-weight: 900;
	text-transform: uppercase;
}

nav {
	display: flex;
	align-items: center;
	margin: 0 -15px;
}

nav a {
	display: block;
	margin: 0 15px;
	color: #92A8C8;
}

nav a:hover {
	color: #BAE1F2;
	transition: 0.25s ease;
}
</style>