```html
<!DOCTYPE html>
<html lang="en" class="no-js">
	<head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <meta http-equiv="X-UA-Compatible" content="ie=edge" />
        <title>What is my viewport</title>
        <meta name="description" content="What Is My Viewport &mdash;; A simple online tool for quickly finding the dimensions of your current device's viewport!" />
        <link rel="stylesheet" href="css/normalize.min.css" />
        <link rel="stylesheet" href="css/main.css" />
        <link rel="manifest" href="manifest.json">
	</head>
	<body>
		<aside class="Message" id="BrowserMessage">
                <p>
                You are using an <strong>outdated</strong> browser, accurate results are not
                guaranteed. Please <a href="https://browsehappy.com/">upgrade your browser</a> for a
                better experience.
                </p>
		</aside>
		<main class="Container Main">
			<article class="App">
				<h1 class="App__title">Your viewport size is:</h1>
				<noscript><p>impossible to determine because you have JavaScript disabled or blocked!</p></noscript>
				<p class="Dimensions"><span id="w"></span>&times;<span id="h"></span></p>
			</article>
		</main>
		<footer class="Footer">
                <!-- Togglable footer content -->
		</footer>

		<script async src="js/main.js"></script>
                <!-- Orther <scripta> elements -->
		<script>
                window.addEventListener("load", async event => {
                    if('serviceWorker' in navigator) {
                        await navigator.serviceWorker.register('/sw.js');
                        console.log('[Service Worker] Registered');
                    };
                });
		</script>
	</body>
</html>
```
