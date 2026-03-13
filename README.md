# After_Refresh_Refresh_page_Refresh_effect
### 1.Add on Global/index.css
```jsx
/*==================================== Landing page refresh intro ============================*/
.landing-intro {   /* Used in navabr bottom to top */
    opacity: 0;
    transform: translateY(0px);
    transition: opacity 0.8s ease-out, transform 0.8s ease-out;
    will-change: opacity, transform;
}

.landing-intro-loaded {
    opacity: 1;
    transform: translateY(0);
}

.hero-intro {
    opacity: 0;
    transform: translateY(40px) scale(0.99);
    transition: opacity 1s ease-out 0.15s, transform 1s ease-out 0.15s;
    will-change: opacity, transform;
}

.hero-intro-loaded {
    opacity: 1;
    transform: translateY(0) scale(1);
}

@media (prefers-reduced-motion: reduce) {

    .landing-intro,
    .hero-intro {
        opacity: 1;
        transform: none;
        transition: none;
    }
}
```
### 2. Place css and useEffect on Main Page/ Layout/ Root page

```jsx
const LandingPage = () => {
    const [isLoaded, setIsLoaded] = useState(false)

    useEffect(() => {
        // Reset scroll position on refresh, then trigger intro animation.
        window.scrollTo({ top: 0, left: 0, behavior: 'auto' })
        const timer = setTimeout(() => setIsLoaded(true), 70)

        return () => clearTimeout(timer)
    }, [])


    return (
        <div className={`landing-intro ${isLoaded ? 'landing-intro-loaded' : ''}`}>
            <nav>
                <Navbar />
            </nav>
            <section
                id="home"
                className={`hero-intro ${isLoaded ? 'hero-intro-loaded' : ''}`}
            >
                <HeroPage />
            </section>
            <section id="how-it-work">
                <HowItWork />
            </section>

            <section id="feature">
                <PowerfullFeature />
            </section>

            <section id="transparency">
                <Transparency />
            </section>
            <section id="privacy-security">
                <PrivacyAndSecurity />
            </section>
            <section id="about">
                <AboutPage />
            </section>
            <section id="contact">
                <ContactPaage />
            </section>
            <section id="get-started">
                <PlaystoreDownloadPage />
            </section>

            <section>
                <Footer />
            </section>
        </div>
    )
}

```



## My Utility Repos – Quick Access

Tiny, focused tools I keep reusing. Click → straight to README.

| Repo Name                                      | What it does                              | Updated          | Link                                                                 |
|------------------------------------------------|-------------------------------------------|------------------|----------------------------------------------------------------------|
| After_Refresh_Refresh_page_Refresh_effect      | Smooth intro on page refresh (no blink)   | 3 min ago        |[](https://github.com/Shawon-Reza/After_Refresh_Refresh_page_Refresh_effect#readme) |
| Single_page_Scrolling_Redirect_section         | Smooth navbar section scrolling           | 27 min ago       |[](https://github.com/Shawon-Reza/Single_page_Scrolling_Redirect_section#readme) |
| markdown-language-convert-to-pain-text         | Markdown → plain text converter           | 19 hours ago     |[](https://github.com/Shawon-Reza/markdown-language-convert-to-pain-text#readme) |
| custom-font-                                   | Easy custom font loading                  | yesterday        |[](https://github.com/Shawon-Reza/custom-font-#readme) |
| Dark-light-mood                                | Dark/light mode toggle (simple)           | 2 days ago       |[](https://github.com/Shawon-Reza/Dark-light-mood#readme) |
| Google_Translatation----Language_Switcher----multiLanguage----Free- | Free multi-lang switcher (Google API) | 2 days ago       |[](https://github.com/Shawon-Reza/Google_Translatation----Language_Switcher----multiLanguage----Free-#readme) |
| Middleware---Better_Auth                       | Auth middleware (better auth flow)        | last week        |[](https://github.com/Shawon-Reza/Middleware---Better_Auth#readme) |
| Image-Uploade-using-FromData-base64            | Upload image → Base64                     | Oct 5, 2025      |[](https://github.com/Shawon-Reza/Image-Uploade-using-FromData-base64#readme) |
| outside-click-tracker                          | Detect clicks outside element             | Sep 26, 2025     |[](https://github.com/Shawon-Reza/outside-click-tracker#readme) |
| File-Upload-Csv-xls-xlsx                       | CSV/Excel file upload + parse             | Sep 4, 2025      |[](https://github.com/Shawon-Reza/File-Upload-Csv-xls-xlsx#readme) |
| PDF-Generator-react-pdf-renderer-              | PDF from React components                 | Oct 16, 2025     |[](https://github.com/Shawon-Reza/PDF-Generator-react-pdf-renderer-#readme) |
| get-filtered-data-using-tanstack-query-URLSearchParams | TanStack Query + URL params filter   | Dec 29, 2025     |[](https://github.com/Shawon-Reza/get-filtered-data-using-tanstack-query-URLSearchParams#readme) |
| Refresh-token-access-token-                    | Refresh + access token logic              | Dec 27, 2025     |[](https://github.com/Shawon-Reza/Refresh-token-access-token-#readme) |
| WebSocket_configure                            | Basic WebSocket setup                     | Jan 16           |[](https://github.com/Shawon-Reza/WebSocket_configure#readme) |
| Axios-Instance                                 | Reusable Axios setup (interceptors)       | Jan 16           |[](https://github.com/Shawon-Reza/Axios-Instance#readme) |

**Pro tip:** Sort by "Updated" later—just drag rows. Keeps your dashboard fresh.



















