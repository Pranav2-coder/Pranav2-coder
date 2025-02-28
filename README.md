<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart Agriculture Monitoring</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #16a34a;
            --primary-dark: #15803d;
            --primary-light: #dcfce7;
            --text-dark: #1e293b;
            --text-light: #64748b;
            --white: #ffffff;
            --gray-50: #f9fafb;
            --gray-100: #f3f4f6;
            --gray-200: #e5e7eb;
            --gray-300: #d1d5db;
            --gray-800: #1f2937;
            --green-50: #f0fdf4;
            --green-100: #dcfce7;
            --green-700: #15803d;
            --green-800: #166534;
            --green-900: #14532d;
            --blue-50: #eff6ff;
            --blue-100: #dbeafe;
            --blue-700: #1d4ed8;
            --blue-800: #1e40af;
            --yellow-50: #fefce8;
            --yellow-100: #fef9c3;
            --yellow-700: #a16207;
            --yellow-800: #854d0e;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--text-dark);
            line-height: 1.5;
            background: linear-gradient(to bottom, var(--green-50), var(--white));
            min-height: 100vh;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        /* Header Styles */
        header {
            position: sticky;
            top: 0;
            z-index: 50;
            width: 100%;
            border-bottom: 1px solid var(--gray-200);
            background-color: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(8px);
        }

        .header-container {
            display: flex;
            height: 4rem;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .logo img {
            width: 2rem;
            height: 2rem;
            border-radius: 0.25rem;
        }

        .logo-text {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--green-700);
        }

        nav {
            display: none;
        }

        @media (min-width: 768px) {
            nav {
                display: flex;
                align-items: center;
                gap: 1.5rem;
            }
        }

        nav a {
            font-size: 0.875rem;
            font-weight: 500;
            color: var(--text-dark);
            text-decoration: none;
            transition: color 0.2s;
        }

        nav a:hover {
            color: var(--green-700);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 0.875rem;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 0.375rem;
            cursor: pointer;
            transition: all 0.2s;
            text-decoration: none;
        }

        .btn-primary {
            background-color: var(--green-700);
            color: var(--white);
            border: none;
        }

        .btn-primary:hover {
            background-color: var(--green-800);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--text-dark);
            border: 1px solid var(--gray-300);
        }

        .btn-outline:hover {
            background-color: var(--gray-100);
        }

        .btn-icon {
            padding: 0.5rem;
        }

        .btn svg {
            width: 1rem;
            height: 1rem;
            margin-right: 0.5rem;
        }

        .mobile-menu-btn {
            display: block;
        }

        @media (min-width: 768px) {
            .mobile-menu-btn {
                display: none;
            }

            .btn-contact {
                display: flex;
            }
        }

        .btn-contact {
            display: none;
        }

        /* Hero Section */
        .hero {
            padding: 3rem 0;
            position: relative;
            overflow: hidden;
        }

        @media (min-width: 768px) {
            .hero {
                padding: 6rem 0;
            }
        }

        @media (min-width: 1024px) {
            .hero {
                padding: 8rem 0;
            }
        }

        .hero-bg {
            position: absolute;
            inset: 0;
            background-image: url('https://placehold.co/1920x1080');
            background-size: cover;
            background-position: center;
            opacity: 0.1;
        }

        .hero-container {
            position: relative;
            display: grid;
            gap: 1.5rem;
        }

        @media (min-width: 1024px) {
            .hero-container {
                grid-template-columns: 1fr 400px;
                gap: 3rem;
            }
        }

        @media (min-width: 1280px) {
            .hero-container {
                grid-template-columns: 1fr 500px;
            }
        }

        .hero-content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 1rem;
        }

        .badge {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            background-color: var(--green-100);
            color: var(--green-800);
            border: 1px solid var(--green-200);
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 500;
        }

        .hero-title {
            font-size: 2.25rem;
            font-weight: 700;
            line-height: 1.2;
            color: var(--green-900);
        }

        @media (min-width: 640px) {
            .hero-title {
                font-size: 3rem;
            }
        }

        @media (min-width: 1280px) {
            .hero-title {
                font-size: 3.75rem;
            }
        }

        .hero-description {
            max-width: 600px;
            color: var(--text-light);
            font-size: 1rem;
        }

        @media (min-width: 768px) {
            .hero-description {
                font-size: 1.125rem;
            }
        }

        .hero-actions {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        @media (min-width: 400px) {
            .hero-actions {
                flex-direction: row;
            }
        }

        .card {
            background-color: var(--white);
            border-radius: 0.5rem;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        .farmer-card {
            width: 100%;
            max-width: 24rem;
            margin: 0 auto;
        }

        .card-body {
            padding: 1.5rem;
        }

        .farmer-profile {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .avatar {
            width: 4rem;
            height: 4rem;
            border-radius: 9999px;
            border: 2px solid var(--green-500);
            overflow: hidden;
        }

        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .farmer-info h2 {
            font-size: 1.5rem;
            font-weight: 700;
        }

        .farmer-contact {
            display: flex;
            align-items: center;
            color: var(--text-light);
            font-size: 0.875rem;
            margin-top: 0.25rem;
        }

        .farmer-contact svg {
            width: 1rem;
            height: 1rem;
            margin-right: 0.25rem;
        }

        .farmer-stats {
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px solid var(--gray-200);
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            text-align: center;
        }

        .stat-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--green-700);
        }

        .stat-label {
            font-size: 0.75rem;
            color: var(--text-light);
        }

        /* Farm Stats Section */
        .farm-stats {
            padding: 3rem 0;
            background-color: var(--green-50);
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 2rem;
            color: var(--green-900);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
        }

        @media (min-width: 640px) {
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .stats-grid {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        .stat-card {
            padding: 1.5rem;
        }

        .stat-icon {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
        }

        .stat-title {
            font-size: 1.125rem;
            font-weight: 500;
        }

        .stat-data {
            font-size: 1.875rem;
            font-weight: 700;
            color: var(--green-700);
            margin: 0.5rem 0;
        }

        /* Data Analysis Section */
        .data-analysis {
            padding: 4rem 0;
        }

        @media (min-width: 768px) {
            .data-analysis {
                padding: 6rem 0;
            }
        }

        .analysis-grid {
            display: grid;
            gap: 1.5rem;
            align-items: center;
        }

        @media (min-width: 1024px) {
            .analysis-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 3rem;
            }
        }

        .analysis-content {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .feature-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .feature-item {
            display: flex;
            align-items: flex-start;
        }

        .feature-icon {
            margin-right: 1rem;
            margin-top: 0.25rem;
            background-color: var(--green-100);
            padding: 0.25rem;
            border-radius: 9999px;
        }

        .feature-icon svg {
            width: 1.25rem;
            height: 1.25rem;
            color: var(--green-700);
        }

        .feature-content h3 {
            font-weight: 500;
        }

        .feature-content p {
            font-size: 0.875rem;
            color: var(--text-light);
        }

        .analysis-image {
            position: relative;
            border-radius: 0.5rem;
            overflow: hidden;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        .analysis-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        .gradient-border {
            position: relative;
            border-radius: 0.5rem;
            padding: 1px;
            background: linear-gradient(to right, var(--green-600), var(--blue-600));
        }

        .gradient-border:before {
            content: "";
            position: absolute;
            inset: 0;
            border-radius: 0.5rem;
            padding: 1px;
            background: linear-gradient(to right, var(--green-600), var(--blue-600));
            -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            opacity: 0.25;
            transition: opacity 1s;
        }

        .gradient-border:hover:before {
            opacity: 1;
            transition: opacity 0.2s;
        }

        /* Message Section */
        .message-section {
            padding: 4rem 0;
            background: linear-gradient(to bottom right, var(--green-50), var(--blue-50));
        }

        .text-center {
            text-align: center;
        }

        .section-header {
            margin-bottom: 2.5rem;
        }

        .section-description {
            margin-top: 1rem;
            color: var(--text-light);
            font-size: 1rem;
            max-width: 48rem;
            margin-left: auto;
            margin-right: auto;
        }

        @media (min-width: 768px) {
            .section-description {
                font-size: 1.125rem;
            }
        }

        .message-grid {
            display: grid;
            gap: 1.5rem;
        }

        @media (min-width: 768px) {
            .message-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .message-card {
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .message-icon {
            margin-bottom: 1rem;
            background-color: var(--green-100);
            padding: 0.75rem;
            border-radius: 9999px;
        }

        .message-icon svg {
            width: 2.5rem;
            height: 2.5rem;
            color: var(--green-700);
        }

        .message-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .message-description {
            color: var(--text-light);
            margin-bottom: 1rem;
        }

        .mt-auto {
            margin-top: auto;
        }

        .section-cta {
            margin-top: 3rem;
            text-align: center;
        }

        /* Market Section */
        .market-section {
            padding: 4rem 0;
        }

        @media (min-width: 768px) {
            .market-section {
                padding: 6rem 0;
            }
        }

        .market-grid {
            display: grid;
            gap: 2rem;
        }

        @media (min-width: 768px) {
            .market-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .market-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        .market-card img {
            width: 100%;
            height: 12rem;
            object-fit: cover;
        }

        .w-full {
            width: 100%;
        }

        /* Footer */
        footer {
            background-color: var(--green-900);
            color: var(--white);
            padding: 3rem 0;
        }

        .footer-grid {
            display: grid;
            gap: 2rem;
        }

        @media (min-width: 768px) {
            .footer-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .footer-grid {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        .footer-logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .footer-logo img {
            width: 2rem;
            height: 2rem;
            border-radius: 0.25rem;
            background-color: var(--white);
        }

        .footer-description {
            color: var(--green-200);
            margin-bottom: 1rem;
        }

        .social-links {
            display: flex;
            gap: 1rem;
        }

        .social-link {
            width: 1.5rem;
            height: 1.5rem;
            background-color: var(--green-800);
            border-radius: 9999px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--green-200);
            text-decoration: none;
            transition: color 0.2s;
        }

        .social-link:hover {
            color: var(--white);
        }

        .footer-column h3 {
            font-size: 1.125rem;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.5rem;
        }

        .footer-links a {
            color: var(--green-200);
            text-decoration: none;
            transition: color 0.2s;
        }

        .footer-links a:hover {
            color: var(--white);
        }

        .footer-bottom {
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 1px solid var(--green-800);
            text-align: center;
            color: var(--green-200);
        }

        /* Data Analysis Page Styles */
        .data-page {
            background-color: var(--white);
        }

        .back-link {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-right: 1.5rem;
            color: var(--text-dark);
            text-decoration: none;
        }

        .page-title {
            font-size: 1.25rem;
            font-weight: 700;
            color: var(--green-700);
        }

        .data-main {
            padding: 2rem 0;
        }

        .data-grid {
            display: grid;
            gap: 1.5rem;
        }

        @media (min-width: 768px) {
            .data-grid {
                grid-template-columns: 300px 1fr;
            }
        }

        .filter-card {
            padding: 1rem;
            margin-bottom: 1.5rem;
        }

        .filter-title {
            font-size: 1.125rem;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .filter-group {
            margin-bottom: 1rem;
        }

        .filter-label {
            display: block;
            font-size: 0.875rem;
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .filter-select {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid var(--gray-300);
            border-radius: 0.375rem;
            font-size: 0.875rem;
            margin-bottom: 0.5rem;
        }

        .quick-actions {
            padding: 1rem;
        }

        .action-btn {
            display: flex;
            align-items: center;
            width: 100%;
            text-align: left;
            margin-bottom: 0.5rem;
        }

        .tabs {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tab {
            padding: 0.75rem;
            text-align: center;
            background-color: var(--gray-100);
            border: 1px solid var(--gray-200);
            border-radius: 0.375rem;
            cursor: pointer;
            font-size: 0.875rem;
            font-weight: 500;
        }

        .tab.active {
            background-color: var(--white);
            border-color: var(--gray-300);
            box-shadow: 0 1px 2px rgba(0, 0, 0, 0.05);
        }

        .tab-content {
            display: none;
            padding-top: 1rem;
        }

        .tab-content.active {
            display: block;
        }

        .charts-grid {
            display: grid;
            gap: 1.5rem;
        }

        @media (min-width: 768px) {
            .charts-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        .chart-card {
            padding: 1rem;
        }

        .chart-title {
            font-size: 1.125rem;
            font-weight: 500;
            margin-bottom: 1rem;
        }

        .chart-container {
            aspect-ratio: 4/3;
            background-color: var(--gray-100);
            border-radius: 0.375rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .chart-container img {
            width: 100%;
            height: auto;
        }

        .chart-description {
            font-size: 0.875rem;
            color: var(--text-light);
            margin-top: 1rem;
        }

        .data-table {
            width: 100%;
            border-collapse: collapse;
        }

        .data-table th {
            background-color: var(--green-50);
            text-align: left;
            padding: 0.5rem 1rem;
            border: 1px solid var(--gray-300);
        }

        .data-table td {
            padding: 0.5rem 1rem;
            border: 1px solid var(--gray-300);
        }

        .data-table tr:nth-child(even) {
            background-color: var(--gray-50);
        }

        .table-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1rem;
            font-size: 0.875rem;
        }

        .pagination {
            display: flex;
            gap: 0.5rem;
        }

        .insights-card {
            padding: 1.5rem;
        }

        .insights-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .insights-icon {
            width: 3rem;
            height: 3rem;
            background-color: var(--green-100);
            border-radius: 9999px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .insights-icon svg {
            width: 1.5rem;
            height: 1.5rem;
            color: var(--green-700);
        }

        .insights-title {
            font-size: 1.25rem;
            font-weight: 700;
        }

        .insights-subtitle {
            color: var(--text-light);
        }

        .insight-alert {
            padding: 1rem;
            border-radius: 0.375rem;
            margin-bottom: 1.5rem;
        }

        .insight-alert-blue {
            background-color: var(--blue-50);
            border: 1px solid var(--blue-200);
        }

        .insight-alert-yellow {
            background-color: var(--yellow-50);
            border: 1px solid var(--yellow-200);
        }

        .insight-alert-green {
            background-color: var(--green-50);
            border: 1px solid var(--green-200);
        }

        .insight-alert-title {
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .insight-alert-blue .insight-alert-title {
            color: var(--blue-800);
        }

        .insight-alert-yellow .insight-alert-title {
            color: var(--yellow-800);
        }

        .insight-alert-green .insight-alert-title {
            color: var(--green-800);
        }

        .insight-alert-content {
            margin-bottom: 0.5rem;
        }

        .insight-alert-blue .insight-alert-content {
            color: var(--blue-700);
        }

        .insight-alert-yellow .insight-alert-content {
            color: var(--yellow-700);
        }

        .insight-alert-green .insight-alert-content {
            color: var(--green-700);
        }

        .insight-alert-actions {
            display: flex;
            justify-content: flex-end;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .recommendations-card {
            padding: 1.5rem;
        }

        .recommendations-title {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .recommendation-list {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .overflow-x-auto {
            overflow-x: auto;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">
                <img src="https://placehold.co/32x32" alt="AgriSmart Logo">
                <span class="logo-text">AgriSmart</span>
            </div>
            
            <nav>
                <a href="#">Dashboard</a>
                <a href="#data-analysis">Data Analysis</a>
                <a href="#messages">Messages</a>
                <a href="#market">Market</a>
            </nav>
            
            <div class="header-actions">
                <a href="#" class="btn btn-outline btn-contact">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                        <polyline points="22,6 12,13 2,6"></polyline>
                    </svg>
                    Contact Support
                </a>
                <a href="#" class="btn btn-primary">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <line x1="18" y1="20" x2="18" y2="10"></line>
                        <line x1="12" y1="20" x2="12" y2="4"></line>
                        <line x1="6" y1="20" x2="6" y2="14"></line>
                    </svg>
                    Live Monitoring
                </a>
                <button class="btn btn-outline btn-icon mobile-menu-btn">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <line x1="3" y1="12" x2="21" y2="12"></line>
                        <line x1="3" y1="6" x2="21" y2="6"></line>
                        <line x1="3" y1="18" x2="21" y2="18"></line>
                    </svg>
                </button>
            </div  x2="21" y2="18"></line>
                    </svg>
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="container hero-container">
            <div class="hero-content">
                <span class="badge">Smart Agriculture</span>
                <h1 class="hero-title">Welcome to Your Smart Farm Dashboard</h1>
                <p class="hero-description">
                    Monitor, analyze, and optimize your farm operations with real-time data and smart automation.
                </p>
                <div class="hero-actions">
                    <a href="#" class="btn btn-primary">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <line x1="18" y1="20" x2="18" y2="10"></line>
                            <line x1="12" y1="20" x2="12" y2="4"></line>
                            <line x1="6" y1="20" x2="6" y2="14"></line>
                        </svg>
                        View Farm Analytics
                    </a>
                    <a href="#" class="btn btn-outline">Take a Tour</a>
                </div>
            </div>
            <div class="farmer-card card">
                <div class="card-body">
                    <div class="farmer-profile">
                        <div class="avatar">
                            <img src="https://placehold.co/64x64" alt="John Doe">
                        </div>
                        <div class="farmer-info">
                            <h2>John Doe</h2>
                            <div class="farmer-contact">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path>
                                    <polyline points="22,6 12,13 2,6"></polyline>
                                </svg>
                                <span>john.doe@example.com</span>
                            </div>
                            <div class="farmer-contact">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                                    <circle cx="12" cy="10" r="3"></circle>
                                </svg>
                                <span>Heartland Farm, Iowa, USA</span>
                            </div>
                        </div>
                    </div>
                    <div class="farmer-stats">
                        <div>
                            <div class="stat-value">120</div>
                            <div class="stat-label">Acres</div>
                        </div>
                        <div>
                            <div class="stat-value">4</div>
                            <div class="stat-label">Crops</div>
                        </div>
                        <div>
                            <div class="stat-value">8</div>
                            <div class="stat-label">Sensors</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Farm Stats Section -->
    <section class="farm-stats">
        <div class="container">
            <h2 class="section-title">Farm Monitoring Statistics</h2>
            <div class="stats-grid">
                <div class="card stat-card">
                    <div class="stat-icon">💧</div>
                    <h3 class="stat-title">Soil Moisture</h3>
                    <div class="stat-data">68%</div>
                    <span class="badge">Optimal</span>
                </div>
                <div class="card stat-card">
                    <div class="stat-icon">🌡️</div>
                    <h3 class="stat-title">Temperature</h3>
                    <div class="stat-data">24°C</div>
                    <span class="badge">Normal</span>
                </div>
                <div class="card stat-card">
                    <div class="stat-icon">💨</div>
                    <h3 class="stat-title">Humidity</h3>
                    <div class="stat-data">62%</div>
                    <span class="badge">Good</span>
                </div>
                <div class="card stat-card">
                    <div class="stat-icon">☀️</div>
                    <h3 class="stat-title">Sunlight</h3>
                    <div class="stat-data">85%</div>
                    <span class="badge">Excellent</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Data Analysis Section -->
    <section id="data-analysis" class="data-analysis">
        <div class="container">
            <div class="analysis-grid">
                <div class="analysis-content">
                    <span class="badge">Smart Automation</span>
                    <h2 class="section-title" style="text-align: left;">Data-Driven Farming Decisions</h2>
                    <p>
                        Our advanced analytics platform processes data from your farm sensors to provide actionable insights. 
                        Optimize irrigation, predict crop health issues, and maximize your yield with AI-powered recommendations.
                    </p>
                    <div class="feature-list">
                        <div class="feature-item">
                            <div class="feature-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <polyline points="20 6 9 17 4 12"></polyline>
                                </svg>
                            </div>
                            <div class="feature-content">
                                <h3>Predictive Analytics</h3>
                                <p>Forecast weather patterns and crop yields</p>
                            </div>
                        </div>
                        <div class="feature-item">
                            <div class="feature-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <polyline points="20 6 9 17 4 12"></polyline>
                                </svg>
                            </div>
                            <div class="feature-content">
                                <h3>Automated Irrigation</h3>
                                <p>Save water with smart scheduling based on soil data</p>
                            </div>
                        </div>
                        <div class="feature-item">
                            <div class="feature-icon">
                                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <polyline points="20 6 9 17 4 12"></polyline>
                                </svg>
                            </div>
                            <div class="feature-content">
                                <h3>Pest Detection</h3>
                                <p>Early warning system for potential infestations</p>
                            </div>
                        </div>
                    </div>
                    <div class="hero-actions">
                        <a href="data-analysis.html" class="btn btn-primary">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <line x1="18" y1="20" x2="18" y2="10"></line>
                                <line x1="12" y1="20" x2="12" y2="4"></line>
                                <line x1="6" y1="20" x2="6" y2="14"></line>
                            </svg>
                            Analyze Farm Data
                        </a>
                        <a href="#" class="btn btn-outline">View Historical Data</a>
                    </div>
                </div>
                <div class="gradient-border">
                    <div class="analysis-image">
                        <img src="https://placehold.co/800x600" alt="Data Analysis Dashboard">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Message Section -->
    <section id="messages" class="message-section">
        <div class="container">
            <div class="section-header text-center">
                <span class="badge">Communication</span>
                <h2 class="section-title">Stay Connected with Your Team</h2>
                <p class="section-description">
                    Coordinate farm operations, get expert advice, and communicate with suppliers through our integrated messaging platform.
                </p>
            </div>
            
            <div class="message-grid">
                <div class="card message-card">
                    <div class="message-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
                            <circle cx="9" cy="7" r="4"></circle>
                            <path d="M23 21v-2a4 4 0 0 0-3-3.87"></path>
                            <path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
                        </svg>
                    </div>
                    <h3 class="message-title">Team Collaboration</h3>
                    <p class="message-description">Coordinate with farm workers and managers</p>
                    <a href="#" class="btn btn-outline mt-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
                        </svg>
                        Open Chat
                    </a>
                </div>
                <div class="card message-card">
                    <div class="message-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path>
                            <path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path>
                        </svg>
                    </div>
                    <h3 class="message-title">Expert Consultations</h3>
                    <p class="message-description">Connect with agricultural specialists</p>
                    <a href="#" class="btn btn-outline mt-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
                        </svg>
                        Open Chat
                    </a>
                </div>
                <div class="card message-card">
                    <div class="message-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <circle cx="12" cy="12" r="10"></circle>
                            <line x1="2" y1="12" x2="22" y2="12"></line>
                            <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path>
                        </svg>
                    </div>
                    <h3 class="message-title">Supplier Communication</h3>
                    <p class="message-description">Order supplies and coordinate deliveries</p>
                    <a href="#" class="btn btn-outline mt-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
                        </svg>
                        Open Chat
                    </a>
                </div>
            </div>
            
            <div class="section-cta">
                <a href="messages.html" class="btn btn-primary">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
                    </svg>
                    Message Center
                </a>
            </div>
        </div>
    </section>

    <!-- Market Section -->
    <section id="market" class="market-section">
        <div class="container">
            <div class="section-header text-center">
                <span class="badge">Marketplace</span>
                <h2 class="section-title">Connect with Buyers and Suppliers</h2>
                <p class="section-description">
                    Access real-time market prices, find buyers for your produce, and purchase supplies at competitive rates.
                </p>
            </div>
            
            <div class="market-grid">
                <div class="card market-card">
                    <img src="https://placehold.co/300x200" alt="Crop Market Prices">
                    <div class="card-body">
                        <h3 class="message-title">Crop Market Prices</h3>
                        <p class="message-description">Real-time pricing data for your crops</p>
                        <a href="#" class="btn btn-outline w-full">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <circle cx="9" cy="21" r="1"></circle>
                                <circle cx="20" cy="21" r="1"></circle>
                                <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                            </svg>
                            View Market Trends
                        </a>
                    </div>
                </div>
                <div class="card market-card">
                    <img src="https://placehold.co/300x200" alt="Find Buyers">
                    <div class="card-body">
                        <h3 class="message-title">Find Buyers</h3>
                        <p class="message-description">Connect with local and international buyers</p>
                        <a href="#" class="btn btn-outline w-full">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <circle cx="9" cy="21" r="1"></circle>
                                <circle cx="20" cy="21" r="1"></circle>
                                <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                            </svg>
                            Explore Opportunities
                        </a>
                    </div>
                </div>
                <div class="card market-card">
                    <img src="https://placehold.co/300x200" alt="Purchase Supplies">
                    <div class="card-body">
                        <h3 class="message-title">Purchase Supplies</h3>
                        <p class="message-description">Seeds, fertilizers, and equipment at competitive prices</p>
                        <a href="#" class="btn btn-outline w-full">
                            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                <circle cx="9" cy="21" r="1"></circle>
                                <circle cx="20" cy="21" r="1"></circle>
                                <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                            </svg>
                            Shop Now
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="section-cta">
                <a href="marketplace.html" class="btn btn-primary">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="9" cy="21" r="1"></circle>
                        <circle cx="20" cy="21" r="1"></circle>
                        <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                    </svg>
                    Visit Marketplace
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-grid">
                <div>
                    <div class="footer-logo">
                        <img src="https://placehold.co/32x32" alt="AgriSmart Logo">
                        <span class="text-xl font-bold">AgriSmart</span>
                    </div>
                    <p class="footer-description">
                        Empowering farmers with smart technology for sustainable and profitable agriculture.
                    </p>
                    <div class="social-links">
                        <a href="#twitter" class="social-link">
                            <span class="sr-only">Twitter</span>
                            <span>T</span>
                        </a>
                        <a href="#facebook" class="social-link">
                            <span class="sr-only">Facebook</span>
                            <span>F</span>
                        </a>
                        <a href="#instagram" class="social-link">
                            <span class="sr-only">Instagram</span>
                            <span>I</span>
                        </a>
                        <a href="#linkedin" class="social-link">
                            <span class="sr-only">LinkedIn</span>
                            <span>L</span>
                        </a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Product</h3>
                    <ul class="footer-links">
                        <li><a href="#">Features</a></li>
                        <li><a href="#">Pricing</a></li>
                        <li><a href="#">Case Studies</a></li>
                        <li><a href="#">Documentation</a></li>
                        <li><a href="#">Resources</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Company</h3>
                    <ul class="footer-links">
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Careers</a></li>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Press</a></li>
                        <li><a href="#">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Legal</h3>
                    <ul class="footer-links">
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Cookie Policy</a></li>
                        <li><a href="#">Data Processing</a></li>
                        <li><a href="#">FAQ</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; <script>document.write(new Date().getFullYear())</script> AgriSmart. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple tab functionality for data analysis page
        document.addEventListener('DOMContentLoaded', function() {
            // Mobile menu toggle
            const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
            if (mobileMenuBtn) {
                mobileMenuBtn.addEventListener('click', function() {
                    // Mobile menu functionality would go here
                    alert('Mobile menu clicked');
                });
            }
            
            // Add animation classes to cards on scroll
            const animateOnScroll = function() {
                const cards = document.querySelectorAll('.card');
                cards.forEach(card => {
                    const cardPosition = card.getBoundingClientRect().top;
                    const screenPosition = window.innerHeight / 1.3;
                    
                    if (cardPosition < screenPosition) {
                        card.style.opacity = '1';
                        card.style.transform = 'translateY(0)';
                    }
                });
            };
            
            // Set initial styles for animation
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
            });
            
            // Run on load
            animateOnScroll();
            
            // Run on scroll
            window.addEventListener('scroll', animateOnScroll);
        });
    </script>
</body>
</html>
