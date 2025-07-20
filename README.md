# page.shop.liquid
<!-- Template: page.shop.liquid - Page Shop style TRUFF avec couleurs Harley -->

<style>
    /* Variables couleurs Harley Vape */
    :root {
        --harley-orange: #FF8E20;
        --harley-orange-dark: #E67A1A;
        --harley-cream: #FFF8DC;
        --harley-cream-light: #FFFEF7;
        --harley-brown: #8B4513;
        --harley-brown-light: #A0522D;
        --harley-border: #DEB887;
        --harley-text-dark: #5D4E37;
        --harley-transition: all 0.3s ease;
    }

    /* Container principal */
    .shop-container {
        max-width: 1400px;
        margin: 0 auto;
        padding: 0;
        display: flex;
        min-height: 100vh;
    }

    /* Navigation latérale style TRUFF mais couleurs Harley */
    .sidebar-nav {
        width: 280px;
        background: linear-gradient(145deg, var(--harley-cream-light), var(--harley-cream));
        border-right: 2px solid var(--harley-border);
        padding: 40px 30px;
        position: sticky;
        top: 0;
        height: 100vh;
        overflow-y: auto;
    }

    .nav-title {
        font-size: 2rem;
        font-weight: bold;
        color: var(--harley-brown);
        margin-bottom: 40px;
        text-align: center;
    }

    .nav-menu {
        list-style: none;
    }

    .nav-item {
        margin-bottom: 8px;
    }

    .nav-link {
        display: block;
        padding: 15px 20px;
        color: var(--harley-text-dark);
        text-decoration: none;
        font-weight: 600;
        font-size: 1rem;
        border-radius: 10px;
        transition: var(--harley-transition);
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    .nav-link:hover,
    .nav-link.active {
        background: var(--harley-orange);
        color: white;
        transform: translateX(5px);
        text-decoration: none;
    }

    /* Boutons d'action style TRUFF */
    .action-buttons {
        margin-top: 40px;
    }

    .action-btn {
        display: block;
        width: 100%;
        padding: 15px;
        margin-bottom: 15px;
        background: transparent;
        border: 2px solid var(--harley-brown);
        color: var(--harley-brown);
        text-decoration: none;
        text-align: center;
        font-weight: bold;
        font-size: 0.9rem;
        border-radius: 8px;
        transition: var(--harley-transition);
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    .action-btn:hover {
        background: var(--harley-brown);
        color: white;
        text-decoration: none;
    }

    .action-btn.primary {
        background: var(--harley-orange);
        border-color: var(--harley-orange);
        color: white;
    }

    .action-btn.primary:hover {
        background: var(--harley-orange-dark);
        border-color: var(--harley-orange-dark);
    }

    /* Zone principale */
    .main-content {
        flex: 1;
        padding: 40px;
        background: var(--harley-cream);
    }

    /* Header principal */
    .main-header {
        text-align: center;
        margin-bottom: 50px;
    }

    .main-title {
        font-size: 3.5rem;
        font-weight: bold;
        color: var(--harley-brown);
        margin-bottom: 15px;
        text-shadow: 1px 1px 3px rgba(245, 222, 179, 0.5);
    }

    .main-subtitle {
        font-size: 1.3rem;
        color: var(--harley-orange);
        font-weight: 500;
    }

    /* Grid catégories style TRUFF */
    .categories-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 25px;
        margin-bottom: 60px;
    }

    /* Carte catégorie style TRUFF avec couleurs Harley */
    .category-card {
        background: white;
        border-radius: 15px;
        border: 2px solid var(--harley-border);
        overflow: hidden;
        transition: var(--harley-transition);
        cursor: pointer;
        position: relative;
        box-shadow: 0 5px 20px rgba(255, 142, 32, 0.1);
        display: block;
        text-decoration: none;
        color: inherit;
    }

    .category-card:hover {
        transform: translateY(-8px);
        box-shadow: 0 15px 40px rgba(255, 142, 32, 0.2);
        border-color: var(--harley-orange);
        text-decoration: none;
        color: inherit;
    }

    /* Image catégorie */
    .category-image {
        width: 100%;
        height: 220px;
        background: linear-gradient(45deg, var(--harley-cream-light), var(--harley-cream));
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        border-bottom: 2px solid var(--harley-border);
    }

    .category-placeholder {
        width: 140px;
        height: 160px;
        background: linear-gradient(45deg, var(--harley-orange), var(--harley-orange-dark));
        border-radius: 12px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        font-size: 1rem;
        font-weight: bold;
        text-align: center;
        box-shadow: 0 8px 20px rgba(255, 142, 32, 0.3);
    }

    /* Badge sur image */
    .category-badge {
        position: absolute;
        top: 15px;
        right: 15px;
        background: var(--harley-orange);
        color: white;
        padding: 6px 12px;
        border-radius: 20px;
        font-size: 0.8rem;
        font-weight: bold;
        text-transform: uppercase;
    }

    /* Contenu catégorie */
    .category-content {
        padding: 25px;
    }

    .category-name {
        font-size: 1.4rem;
        font-weight: bold;
        color: var(--harley-brown);
        margin-bottom: 8px;
    }

    .category-description {
        color: var(--harley-text-dark);
        font-size: 0.9rem;
        margin-bottom: 15px;
        line-height: 1.5;
    }

    .category-count {
        color: var(--harley-orange);
        font-weight: 600;
        font-size: 0.9rem;
        margin-bottom: 20px;
    }

    /* Section du bas style TRUFF */
    .bottom-section {
        background: linear-gradient(135deg, var(--harley-cream-light), var(--harley-cream));
        border-radius: 20px;
        border: 2px solid var(--harley-border);
        padding: 50px;
        text-align: center;
        box-shadow: 0 10px 30px rgba(255, 142, 32, 0.1);
    }

    .bottom-title {
        font-size: 2.5rem;
        color: var(--harley-brown);
        margin-bottom: 20px;
        font-weight: bold;
    }

    .bottom-subtitle {
        color: var(--harley-text-dark);
        font-size: 1.2rem;
        margin-bottom: 30px;
    }

    .bottom-btn {
        display: inline-block;
        padding: 18px 40px;
        background: transparent;
        border: 2px solid var(--harley-brown);
        color: var(--harley-brown);
        text-decoration: none;
        font-weight: bold;
        font-size: 1.1rem;
        border-radius: 8px;
        transition: var(--harley-transition);
        text-transform: uppercase;
        letter-spacing: 2px;
    }

    .bottom-btn:hover {
        background: var(--harley-brown);
        color: white;
        transform: translateY(-3px);
        box-shadow: 0 10px 25px rgba(139, 69, 19, 0.3);
        text-decoration: none;
    }

    /* Responsive */
    @media (max-width: 1024px) {
        .shop-container {
            flex-direction: column;
        }

        .sidebar-nav {
            width: 100%;
            height: auto;
            position: relative;
            padding: 20px;
        }

        .nav-menu {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 10px;
        }

        .nav-item {
            margin-bottom: 0;
            min-width: max-content;
        }

        .action-buttons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .action-btn {
            margin-bottom: 0;
        }
    }

    @media (max-width: 768px) {
        .main-content {
            padding: 20px;
        }

        .main-title {
            font-size: 2.5rem;
        }

        .categories-grid {
            grid-template-columns: 1fr;
            gap: 20px;
        }

        .bottom-section {
            padding: 30px 20px;
        }

        .bottom-title {
            font-size: 2rem;
        }
    }

    /* Animations */
    .category-card {
        animation: fadeInUp 0.6s ease-out;
    }

    @keyframes fadeInUp {
        from {
            opacity: 0;
            transform: translateY(30px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }
</style>

<div class="shop-container">
    <!-- Navigation latérale style TRUFF -->
    <nav class="sidebar-nav">
        <h2 class="nav-title">SHOP</h2>
        
        <ul class="nav-menu">
            {% for collection in collections %}
                {% if collection.products_count > 0 %}
                    <li class="nav-item">
                        <a href="{{ collection.url }}" class="nav-link">{{ collection.title | upcase }}</a>
                    </li>
                {% endif %}
            {% endfor %}
        </ul>

        <div class="action-buttons">
            <a href="/collections/bundles" class="action-btn primary">BUILD YOUR BUNDLE</a>
            <a href="/collections/all" class="action-btn">SHOP ALL</a>
        </div>
    </nav>

    <!-- Contenu principal -->
    <main class="main-content">
        <!-- Header principal -->
        <header class="main-header">
            <h1 class="main-title">{{ page.title | default: "PREMIUM VAPE COLLECTION" }}</h1>
            <p class="main-subtitle">{{ page.content | strip_html | default: "Discover our curated selection of premium vaping products" }}</p>
        </header>

        <!-- Grid des catégories -->
        <div class="categories-grid">
            {% comment %} Collections dynamiques {% endcomment %}
            {% assign featured_collections = 'core,fusion,nexus,kits,pods,accessories' | split: ',' %}
            
            {% for collection_handle in featured_collections %}
                {% assign collection = collections[collection_handle] %}
                {% if collection and collection.products_count > 0 %}
                    <a href="{{ collection.url }}" class="category-card">
                        <div class="category-image">
                            {% if forloop.first %}
                                <div class="category-badge">Popular</div>
                            {% elsif forloop.index == 2 %}
                                <div class="category-badge">Best Value</div>
                            {% elsif collection.tags contains 'new' %}
                                <div class="category-badge">New</div>
                            {% endif %}
                            
                            {% if collection.featured_image %}
                                <img src="{{ collection.featured_image | img_url: '300x300' }}" 
                                     alt="{{ collection.title }}"
                                     style="width: 140px; height: 160px; object-fit: cover; border-radius: 12px;">
                            {% else %}
                                <div class="category-placeholder">
                                    {% case collection_handle %}
                                        {% when 'core' %}
                                            🧪<br><br>E-LIQUIDS<br>CORE<br>COLLECTION
                                        {% when 'fusion' %}
                                            ⚡<br><br>E-LIQUIDS<br>FUSION<br>PREMIUM
                                        {% when 'nexus' %}
                                            💫<br><br>E-LIQUIDS<br>NEXUS<br>SERIES
                                        {% when 'kits' %}
                                            📦<br><br>STARTER<br>KITS<br>COMPLETE
                                        {% when 'pods' %}
                                            💨<br><br>PODS<br>SYSTEMS<br>PREMIUM
                                        {% when 'accessories' %}
                                            🔧<br><br>VAPE<br>ACCESSORIES<br>PREMIUM
                                        {% else %}
                                            🏍️<br><br>{{ collection.title | upcase | replace: ' ', '<br>' }}
                                    {% endcase %}
                                </div>
                            {% endif %}
                        </div>
                        <div class="category-content">
                            <h3 class="category-name">{{ collection.title | upcase }}</h3>
                            <p class="category-description">
                                {% if collection.description != blank %}
                                    {{ collection.description | strip_html | truncate: 100 }}
                                {% else %}
                                    {% case collection_handle %}
                                        {% when 'core' %}
                                            Premium e-liquids with authentic flavors. Natural ingredients, no artificial colors.
                                        {% when 'fusion' %}
                                            Advanced fusion flavors with complex profiles. Premium ingredients and smooth delivery.
                                        {% when 'nexus' %}
                                            Next-generation e-liquids with innovative flavor combinations.
                                        {% when 'kits' %}
                                            Complete starter kits with everything you need. Perfect for beginners and pros.
                                        {% when 'pods' %}
                                            High-quality pod systems. Easy to use, great flavor, reliable performance.
                                        {% when 'accessories' %}
                                            Essential vaping accessories. Coils, tanks, tools and more for your setup.
                                        {% else %}
                                            Discover our {{ collection.title | downcase }} collection.
                                    {% endcase %}
                                {% endif %}
                            </p>
                            <div class="category-count">{{ collection.products_count }}+ produit{% if collection.products_count > 1 %}s{% endif %} disponibles</div>
                        </div>
                    </a>
                {% endif %}
            {% endfor %}

            {% comment %} Collections supplémentaires s'il y en a {% endcomment %}
            {% for collection in collections %}
                {% unless featured_collections contains collection.handle %}
                    {% if collection.products_count > 0 and forloop.index <= 8 %}
                        <a href="{{ collection.url }}" class="category-card">
                            <div class="category-image">
                                {% if collection.featured_image %}
                                    <img src="{{ collection.featured_image | img_url: '300x300' }}" 
                                         alt="{{ collection.title }}"
                                         style="width: 140px; height: 160px; object-fit: cover; border-radius: 12px;">
                                {% else %}
                                    <div class="category-placeholder">
                                        🏍️<br><br>{{ collection.title | upcase | replace: ' ', '<br>' }}
                                    </div>
                                {% endif %}
                            </div>
                            <div class="category-content">
                                <h3 class="category-name">{{ collection.title | upcase }}</h3>
                                <p class="category-description">
                                    {{ collection.description | strip_html | truncate: 100 | default: "Découvrez notre collection " | append: collection.title | append: "." }}
                                </p>
                                <div class="category-count">{{ collection.products_count }}+ produit{% if collection.products_count > 1 %}s{% endif %} disponibles</div>
                            </div>
                        </a>
                    {% endif %}
                {% endunless %}
            {% endfor %}
        </div>

        <!-- Section du bas -->
        <section class="bottom-section">
            <h2 class="bottom-title">Learn More</h2>
            <p class="bottom-subtitle">Discover the world of premium vaping with our expertly curated collection</p>
            <a href="/collections/all" class="bottom-btn">EXPLORE COLLECTION</a>
        </section>
    </main>
</div>

<script>
// Navigation active et animations
document.addEventListener('DOMContentLoaded', function() {
    const navLinks = document.querySelectorAll('.nav-link');
    const categoryCards = document.querySelectorAll('.category-card');

    // Animation d'entrée séquentielle
    categoryCards.forEach((card, index) => {
        card.style.animationDelay = `${index * 0.1}s`;
    });

    // Hover effects avancés
    categoryCards.forEach(card => {
        card.addEventListener('mouseenter', function() {
            this.style.transform = 'translateY(-12px) scale(1.02)';
        });

        card.addEventListener('mouseleave', function() {
            this.style.transform = 'translateY(0) scale(1)';
        });
    });
});
</script>
