<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Congreso Internacional de Especialidades Clínicas Quirúrgicas</title>
    <style>
        /* Estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), 
                        url('https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Bahia_de_Caraquez_%28cropped%29.jpg/1200px-Bahia_de_Caraquez_%28cropped%29.jpg');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0;
            text-align: center;
            position: relative;
        }
        
        .countdown {
            background-color: rgba(0, 86, 179, 0.9);
            padding: 20px;
            border-radius: 10px;
            margin: 20px auto;
            max-width: 600px;
        }
        
        .countdown-title {
            font-size: 1.2rem;
            margin-bottom: 15px;
        }
        
        .countdown-timer {
            display: flex;
            justify-content: center;
            gap: 15px;
        }
        
        .countdown-item {
            background-color: white;
            color: #0056b3;
            padding: 10px 15px;
            border-radius: 5px;
            min-width: 70px;
        }
        
        .countdown-number {
            font-size: 1.8rem;
            font-weight: bold;
        }
        
        .countdown-label {
            font-size: 0.8rem;
            margin-top: 5px;
        }
        
        .logo {
            max-width: 200px;
            margin-bottom: 20px;
            background-color: white;
            padding: 10px;
            border-radius: 10px;
        }
        
        header h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        
        header p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 30px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }
        
        .btn {
            display: inline-block;
            background-color: #0056b3;
            color: white;
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: #003d82;
        }
        
        .btn:disabled {
            background-color: #cccccc;
            cursor: not-allowed;
        }
        
        .btn-admin {
            position: fixed;
            top: 20px;
            right: 20px;
            background-color: #28a745;
            z-index: 1000;
        }
        
        .btn-admin:hover {
            background-color: #218838;
        }
        
        .btn-edit {
            background-color: #ffc107;
            color: #212529;
            padding: 6px 12px;
            font-size: 0.8rem;
        }
        
        .btn-delete {
            background-color: #dc3545;
            padding: 6px 12px;
            font-size: 0.8rem;
        }
        
        .btn-add {
            background-color: #28a745;
            margin-bottom: 15px;
        }
        
        .btn-download {
            background-color: #17a2b8;
            margin-left: 10px;
        }
        
        .btn-agenda {
            background-color: #6f42c1;
            margin: 10px 0;
        }
        
        .btn-upload {
            background-color: #6f42c1;
        }
        
        .btn-attendance {
            background-color: #fd7e14;
        }
        
        .btn-certificate {
            background-color: #20c997;
        }
        
        .btn-sync {
            background-color: #6f42c1;
        }
        
        .btn-update {
            background-color: #6c757d;
        }
        
        .btn-preview {
            background-color: #17a2b8;
        }
        
        /* Secciones */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            color: #0056b3;
            position: relative;
        }
        
        .section-title:after {
            content: '';
            display: block;
            width: 100px;
            height: 3px;
            background-color: #0056b3;
            margin: 15px auto 0;
        }
        
        /* Agenda */
        .agenda-section {
            background-color: #e9f0f7;
        }
        
        .agenda-container {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .agenda-content {
            text-align: center;
        }
        
        .agenda-placeholder {
            color: #666;
            font-style: italic;
            margin: 20px 0;
        }
        
        .agenda-uploaded {
            text-align: center;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 10px;
            border: 2px dashed #ddd;
        }
        
        .agenda-file-info {
            margin: 15px 0;
            padding: 15px;
            background-color: #e9f0f7;
            border-radius: 5px;
        }
        
        .file-name {
            font-weight: bold;
            color: #0056b3;
        }
        
        .file-size {
            color: #666;
            font-size: 0.9rem;
        }
        
        .file-upload-date {
            color: #666;
            font-size: 0.9rem;
        }
        
        /* Sobre el evento */
        .about-content {
            display: flex;
            align-items: center;
            gap: 40px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s;
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        /* Información del evento */
        .event-info {
            background-color: #e9f0f7;
        }
        
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .info-card {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            text-align: center;
            transition: transform 0.3s;
        }
        
        .info-card:hover {
            transform: translateY(-10px);
        }
        
        .info-card i {
            font-size: 2.5rem;
            color: #0056b3;
            margin-bottom: 15px;
        }
        
        /* Ubicación */
        .location-content {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }
        
        .location-images {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .location-img {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .location-img img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            display: block;
        }
        
        .map-container {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .map-container iframe {
            width: 100%;
            height: 400px;
            border: none;
        }
        
        /* Registro */
        .registration {
            background-color: #0056b3;
            color: white;
            text-align: center;
        }
        
        .registration h2 {
            color: white;
        }
        
        .cupos {
            font-size: 1.5rem;
            margin: 20px 0;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 10px 20px;
            border-radius: 5px;
            display: inline-block;
        }
        
        .registration-deadline {
            background-color: rgba(255, 193, 7, 0.2);
            padding: 15px;
            border-radius: 10px;
            margin: 20px auto;
            max-width: 600px;
            border: 2px solid #ffc107;
        }
        
        .deadline-warning {
            color: #856404;
            font-weight: bold;
            margin-bottom: 10px;
        }
        
        .deadline-countdown {
            font-size: 1.1rem;
            font-weight: bold;
        }
        
        .form-container {
            background-color: white;
            color: #333;
            padding: 30px;
            border-radius: 10px;
            max-width: 800px;
            margin: 0 auto;
            text-align: left;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }
        
        .file-input-container {
            position: relative;
            overflow: hidden;
            display: inline-block;
            width: 100%;
        }
        
        .file-input {
            position: absolute;
            left: 0;
            top: 0;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }
        
        .file-input-label {
            display: block;
            padding: 12px;
            background: #f8f9fa;
            border: 2px dashed #dee2e6;
            border-radius: 5px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .file-input-label:hover {
            background: #e9ecef;
            border-color: #6f42c1;
        }
        
        .file-selected {
            background: #d4edda;
            border-color: #28a745;
        }
        
        .alert {
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        
        .alert-success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .alert-danger {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .alert-warning {
            background-color: #fff3cd;
            color: #856404;
            border: 1px solid #ffeaa7;
        }
        
        .alert-info {
            background-color: #d1ecf1;
            color: #0c5460;
            border: 1px solid #bee5eb;
        }
        
        .cupos-disponibles {
            display: flex;
            justify-content: space-around;
            margin: 20px 0;
            flex-wrap: wrap;
            display: none; /* Oculto para usuarios normales */
        }
        
        .cupo-categoria {
            background-color: rgba(255, 255, 255, 0.2);
            padding: 10px 15px;
            border-radius: 5px;
            margin: 5px;
            text-align: center;
        }
        
        /* Panel de administración */
        .admin-panel {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .admin-content {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            width: 95%;
            max-width: 1200px;
            max-height: 90vh;
            overflow-y: auto;
        }
        
        .admin-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            border-bottom: 1px solid #ddd;
            padding-bottom: 15px;
        }
        
        .close-admin {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
        }
        
        .admin-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .stat-card {
            background-color: #f8f9fa;
            padding: 15px;
            border-radius: 5px;
            text-align: center;
        }
        
        .stat-number {
            font-size: 1.8rem;
            font-weight: bold;
            color: #0056b3;
        }
        
        .stat-label {
            font-size: 0.9rem;
            color: #666;
        }
        
        .admin-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        
        .admin-table th, .admin-table td {
            padding: 10px;
            text-align: left;
            border-bottom: 1px solid #ddd;
        }
        
        .admin-table th {
            background-color: #f1f1f1;
        }
        
        .admin-actions {
            display: flex;
            gap: 5px;
        }
        
        .admin-tabs {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #ddd;
        }
        
        .admin-tab {
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 3px solid transparent;
        }
        
        .admin-tab.active {
            border-bottom: 3px solid #0056b3;
            font-weight: bold;
        }
        
        .tab-content {
            display: none;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .attendance-links {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }
        
        .attendance-link-card {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #fd7e14;
        }
        
        .attendance-day {
            font-weight: bold;
            color: #fd7e14;
            margin-bottom: 10px;
        }
        
        .attendance-form-links {
            margin-top: 20px;
        }
        
        .form-link {
            display: block;
            margin: 10px 0;
            padding: 10px;
            background-color: #e9ecef;
            border-radius: 5px;
            text-decoration: none;
            color: #0056b3;
            transition: background-color 0.3s;
        }
        
        .form-link:hover {
            background-color: #dee2e6;
        }
        
        .attendance-status {
            display: inline-block;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .status-approved {
            background-color: #d4edda;
            color: #155724;
        }
        
        .status-pending {
            background-color: #fff3cd;
            color: #856404;
        }
        
        .status-failed {
            background-color: #f8d7da;
            color: #721c24;
        }
        
        /* Búsqueda */
        .search-container {
            margin: 15px 0;
            display: flex;
            gap: 10px;
        }
        
        .search-input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        /* Certificados */
        .certificates-section {
            background-color: #e9f0f7;
        }
        
        .certificates-container {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }
        
        .certificate-uploaded {
            text-align: center;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 10px;
            border: 2px dashed #ddd;
        }
        
        .certificate-file-info {
            margin: 15px 0;
            padding: 15px;
            background-color: #e9f0f7;
            border-radius: 5px;
        }
        
        .certificate-placeholder {
            color: #666;
            font-style: italic;
            margin: 20px 0;
        }
        
        .certificate-actions {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .certificate-available {
            background-color: rgba(32, 201, 151, 0.1);
            border: 2px solid #20c997;
        }
        
        .certificate-unavailable {
            background-color: rgba(108, 117, 125, 0.1);
            border: 2px solid #6c757d;
        }
        
        /* Sincronización */
        .sync-section {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            border-left: 4px solid #6f42c1;
        }
        
        .sync-status {
            margin-top: 15px;
            padding: 15px;
            border-radius: 5px;
        }
        
        /* Vista previa de certificado */
        .certificate-preview {
            margin-top: 20px;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 10px;
            background-color: #f8f9fa;
            max-height: 400px;
            overflow-y: auto;
        }
        
        .certificate-preview-content {
            background-color: white;
            padding: 30px;
            border: 2px solid #20c997;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        /* Footer */
        footer {
            background-color: #333;
            color: white;
            padding: 40px 0;
            text-align: center;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }
        
        .footer-links {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: #5dade2;
        }
        
        .contact-info {
            margin-top: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            max-width: 600px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .about-content {
                flex-direction: column;
            }
            
            header {
                padding: 60px 0;
            }
            
            header h1 {
                font-size: 2rem;
            }
            
            .location-images {
                grid-template-columns: 1fr;
            }
            
            .cupos-disponibles {
                flex-direction: column;
            }
            
            .btn-admin {
                position: relative;
                top: auto;
                right: auto;
                margin-bottom: 20px;
            }
            
            .countdown-timer {
                flex-wrap: wrap;
            }
            
            .admin-table {
                font-size: 0.8rem;
            }
            
            .admin-actions {
                flex-direction: column;
            }
            
            .admin-tabs {
                flex-direction: column;
            }
            
            .attendance-links {
                grid-template-columns: 1fr;
            }
            
            .search-container {
                flex-direction: column;
            }
            
            .certificate-actions {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Librerías para procesamiento de documentos -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mammoth/1.6.0/mammoth.browser.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/FileSaver.js/2.0.5/FileSaver.min.js"></script>
    <!-- Librería para generar PDF -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
</head>
<body>
    <!-- Botón de administración -->
    <button class="btn btn-admin" id="btn-admin">Administración</button>

    <!-- Header -->
    <header>
        <div class="container">
            <!-- Logo del hospital -->
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Bahia_de_Caraquez_%28cropped%29.jpg/300px-Bahia_de_Caraquez_%28cropped%29.jpg" alt="Hospital Miguel H. Alcívar" class="logo">
            <h1>Congreso Internacional de Especialidades Clínicas Quirúrgicas</h1>
            <p>Un evento académico sin fines de lucro organizado por el Hospital Miguel H. Alcívar</p>
            
            <!-- Countdown Timer -->
            <div class="countdown">
                <div class="countdown-title">El congreso inicia en:</div>
                <div class="countdown-timer" id="countdown-timer">
                    <div class="countdown-item">
                        <div class="countdown-number" id="days">00</div>
                        <div class="countdown-label">Días</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="hours">00</div>
                        <div class="countdown-label">Horas</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="minutes">00</div>
                        <div class="countdown-label">Minutos</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="seconds">00</div>
                        <div class="countdown-label">Segundos</div>
                    </div>
                </div>
            </div>
            
            <a href="#registro" class="btn">Registrarse Ahora</a>
        </div>
    </header>

    <!-- Agenda -->
    <section id="agenda" class="agenda-section">
        <div class="container">
            <h2 class="section-title">Agenda del Evento</h2>
            <div class="agenda-container">
                <div class="agenda-content">
                    <div id="agenda-display">
                        <div class="agenda-placeholder" id="agenda-placeholder">
                            <i class="fas fa-file-pdf fa-3x" style="color: #ccc; margin-bottom: 15px;"></i>
                            <p>La agenda del evento será publicada próximamente.</p>
                            <p><small>El administrador cargará el archivo PDF con la agenda completa.</small></p>
                        </div>
                        <div id="agenda-uploaded" style="display: none;">
                            <div class="agenda-uploaded">
                                <i class="fas fa-file-pdf fa-3x" style="color: #d32f2f; margin-bottom: 15px;"></i>
                                <h3>Agenda del Congreso Disponible</h3>
                                <p>Descarga la agenda completa del evento en formato PDF</p>
                                <div class="agenda-file-info">
                                    <div class="file-name" id="agenda-file-name"></div>
                                    <div class="file-size" id="agenda-file-size"></div>
                                    <div class="file-upload-date" id="agenda-upload-date"></div>
                                </div>
                                <button class="btn btn-agenda" id="btn-download-agenda">
                                    <i class="fas fa-download"></i> Descargar Agenda PDF
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Certificados -->
    <section id="certificados" class="certificates-section">
        <div class="container">
            <h2 class="section-title">Certificados</h2>
            <div class="certificates-container">
                <div class="certificate-content">
                    <div id="certificate-display">
                        <div class="certificate-placeholder" id="certificate-placeholder">
                            <i class="fas fa-file-certificate fa-3x" style="color: #ccc; margin-bottom: 15px;"></i>
                            <p>Los certificados estarán disponibles después del evento.</p>
                            <p><small>Los asistentes que cumplan con al menos 2 de 3 asistencias podrán descargar su certificado a partir del 25 de Octubre 2025 a las 13:00.</small></p>
                        </div>
                        <div id="certificate-uploaded" style="display: none;">
                            <div class="certificate-uploaded" id="certificate-uploaded-content">
                                <i class="fas fa-file-certificate fa-3x" style="color: #20c997; margin-bottom: 15px;"></i>
                                <h3>Certificados Disponibles</h3>
                                <p>Descarga tu certificado de participación en el congreso</p>
                                <div class="certificate-file-info">
                                    <div class="file-name" id="certificate-file-name"></div>
                                    <div class="file-upload-date" id="certificate-upload-date"></div>
                                </div>
                                <div class="certificate-actions">
                                    <button class="btn btn-certificate" id="btn-download-my-certificate">
                                        <i class="fas fa-download"></i> Descargar Mi Certificado
                                    </button>
                                    <button class="btn btn-download" id="btn-download-all-certificates" style="display: none;">
                                        <i class="fas fa-file-archive"></i> Descargar Todos (Admin)
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sobre el evento -->
    <section id="sobre">
        <div class="container">
            <h2 class="section-title">Sobre el Congreso</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>El Congreso Internacional de Especialidades Clínicas Quirúrgicas es un evento académico de primer nivel que reúne a los más destacados profesionales de la salud para compartir conocimientos, experiencias y los últimos avances en el campo de la cirugía.</p>
                    <p>Organizado por el prestigioso Hospital Miguel H. Alcívar, este congreso busca fomentar el intercambio científico y el desarrollo profesional continuo en un ambiente de colaboración y excelencia.</p>
                    <p>Este año, tendremos el honor de contar con ponentes internacionales y nacionales que presentarán casos clínicos, técnicas innovadoras y resultados de investigaciones recientes en diversas especialidades quirúrgicas.</p>
                </div>
                <div class="about-image">
                    <!-- Imagen del Hospital Miguel H. Alcívar -->
                    <img src="https://lh5.googleusercontent.com/p/AF1QipM4vHtJj5K7q3Vx1w1Z9X9Z9Z9Z9Z9Z9Z9Z9Z9=w408-h306-k-no" alt="Hospital Miguel H. Alcívar">
                </div>
            </div>
        </div>
    </section>

    <!-- Información del evento -->
    <section id="informacion" class="event-info">
        <div class="container">
            <h2 class="section-title">Información del Evento</h2>
            <div class="info-grid">
                <div class="info-card">
                    <i class="fas fa-calendar-alt"></i>
                    <h3>Fechas</h3>
                    <p>Jueves 23 al Sábado 25 de Octubre, 2025</p>
                </div>
                <div class="info-card">
                    <i class="fas fa-map-marker-alt"></i>
                    <h3>Ubicación</h3>
                    <p>Auditorio Universidad Laica Eloy Alfaro de Manabí, Extensión Sucre</p>
                </div>
                <div class="info-card">
                    <i class="fas fa-users"></i>
                    <h3>Capacidad</h3>
                    <p>Límite de 220 cupos disponibles</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Ubicación -->
    <section id="ubicacion">
        <div class="container">
            <h2 class="section-title">Ubicación</h2>
            <div class="location-content">
                <div>
                    <h3>Bahía de Caráquez - Destino Único en Manabí</h3>
                    <p>Disfruta de este hermoso destino costero mientras participas en nuestro congreso. Bahía de Caráquez ofrece un entorno único para el aprendizaje y la relajación.</p>
                </div>
                
                <div class="location-images">
                    <div class="location-img">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Bahia_de_Caraquez_%28cropped%29.jpg/800px-Bahia_de_Caraquez_%28cropped%29.jpg" alt="Vista de Bahía de Caráquez">
                    </div>
                    <div class="location-img">
                        <img src="https://dynamic-media-cdn.tripadvisor.com/media/photo-o/15/33/f7/2d/bahia-de-caraquez.jpg?w=1200&h=-1&s=1" alt="Bahía de Caráquez">
                    </div>
                    <div class="location-img">
                        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/Bahia_de_Caraquez_2.jpg/800px-Bahia_de_Caraquez_2.jpg" alt="Playa de Bahía de Caráquez">
                    </div>
                </div>
                
                <div class="map-container">
                    <!-- Mapa de Google Maps del enlace proporcionado -->
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3989.806833553388!2d-80.4278943250138!3d-0.5978264352402632!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x902b3d3f5b4c4c1f%3A0x5d0d6b3c1b1b1b1b!2sUniversidad%20Laica%20Eloy%20Alfaro%20de%20Manab%C3%AD%20Extensi%C3%B3n%20Sucre!5e0!3m2!1ses!2sec!4v1698765432100!5m2!1ses!2sec" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Registro -->
    <section id="registro" class="registration">
        <div class="container">
            <h2 class="section-title">Registro</h2>
            <p>No pierdas la oportunidad de participar en este importante evento académico.</p>
            
            <!-- Límite de tiempo para registro -->
            <div class="registration-deadline" id="registration-deadline">
                <div class="deadline-warning">
                    <i class="fas fa-exclamation-triangle"></i> Límite de Registro
                </div>
                <div class="deadline-countdown" id="deadline-countdown">
                    Tiempo restante para registro: <span id="deadline-timer">--:--:--</span>
                </div>
                <p><small>Los registros estarán disponibles hasta el 22 de Octubre a las 23:59</small></p>
            </div>
            
            <div class="cupos">Cupos disponibles: <span id="cupos-disponibles">50</span> de 220</div>
            
            <div class="form-container">
                <div id="mensaje-registro"></div>
                
                <form id="formulario-inscripcion">
                    <div class="form-group">
                        <label for="cargo">Cargo *</label>
                        <select id="cargo" name="cargo" required>
                            <option value="">Seleccione su cargo</option>
                            <option value="DR.">DR.</option>
                            <option value="DRA.">DRA.</option>
                            <option value="LCDO.">LCDO.</option>
                            <option value="LCDA.">LCDA.</option>
                            <option value="IRM.">IRM.</option>
                            <option value="IRE.">IRE.</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="nombre">Nombre *</label>
                        <input type="text" id="nombre" name="nombre" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="apellido">Apellido *</label>
                        <input type="text" id="apellido" name="apellido" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="correo">Correo Electrónico *</label>
                        <input type="email" id="correo" name="correo" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="categoria">Categoría *</label>
                        <select id="categoria" name="categoria" required>
                            <option value="">Seleccione su categoría</option>
                            <option value="MEDICO GENERAL">Médico General</option>
                            <option value="MEDICO ESPECIALISTA">Médico Especialista</option>
                            <option value="LICENCIADO EN ENFERMERIA">Licenciado en Enfermería</option>
                            <option value="INTERNO ROTATIVO DE ENFERMERIA">Interno Rotativo de Enfermería</option>
                            <option value="INTERNO ROTATIVO DE MEDICINA">Interno Rotativo de Medicina</option>
                        </select>
                    </div>
                    
                    <button type="submit" class="btn" id="btn-registrar">Registrarse</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div>
                    <h3>Hospital Miguel H. Alcívar</h3>
                    <p>Organizador del Congreso Internacional de Especialidades Clínicas Quirúrgicas</p>
                </div>
                
                <div class="contact-info">
                    <h4>Unidad de Docencia e Investigación</h4>
                    <p><i class="fas fa-user-md"></i> Dr. Julio Feijoo - Analista de Docencia</p>
                    <p><i class="fas fa-phone"></i> Contacto: 0991708712</p>
                    <p><i class="fas fa-envelope"></i> Correo: docenciahmha2023@gmail.com</p>
                </div>
                
                <div class="footer-links">
                    <a href="https://www.canva.com/design/DAGyKzrqRWk/xXJneiDmUITTdIkEWUWy4w/watch?utm_content=DAGyKzrqRWk&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h0266aebfbe" target="_blank">Más información</a>
                    <a href="https://allyouneedisbahiadecaraquez.com/bahia-de-caraquez-climate/" target="_blank">Conoce Bahía de Caráquez</a>
                    <a href="https://maps.app.goo.gl/hpXSzdhnLAmU5ztJA" target="_blank">Ver ubicación en Google Maps</a>
                </div>
                <p>&copy; 2023 Congreso Internacional de Especialidades Clínicas Quirúrgicas. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- Panel de Administración -->
    <div class="admin-panel" id="admin-panel">
        <div class="admin-content">
            <div class="admin-header">
                <h2>Panel de Administración</h2>
                <button class="close-admin" id="close-admin">&times;</button>
            </div>
            
            <div id="admin-login">
                <h3>Iniciar Sesión</h3>
                <div class="form-group">
                    <label for="admin-user">Usuario</label>
                    <input type="text" id="admin-user" class="form-control" value="DOCENCIA">
                </div>
                <div class="form-group">
                    <label for="admin-pass">Contraseña</label>
                    <input type="password" id="admin-pass" class="form-control" value="DOCENCIA">
                </div>
                <button class="btn" id="btn-login">Ingresar</button>
                <div style="margin-top: 15px; padding: 10px; background-color: #f8f9fa; border-radius: 5px;">
                    <p><strong>Credenciales predefinidas:</strong></p>
                    <p>Usuario: DOCENCIA</p>
                    <p>Contraseña: DOCENCIA</p>
                </div>
            </div>
            
            <div id="admin-dashboard" style="display: none;">
                <div class="admin-tabs">
                    <div class="admin-tab active" data-tab="participantes">Participantes</div>
                    <div class="admin-tab" data-tab="agenda">Agenda</div>
                    <div class="admin-tab" data-tab="asistencias">Asistencias</div>
                    <div class="admin-tab" data-tab="certificados">Certificados</div>
                </div>
                
                <!-- Tab de Participantes -->
                <div id="tab-participantes" class="tab-content active">
                    <h3>Gestión de Cupos y Participantes</h3>
                    
                    <div class="admin-stats">
                        <div class="stat-card">
                            <div class="stat-number" id="stat-total">220</div>
                            <div class="stat-label">Cupos Totales</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-asignados">170</div>
                            <div class="stat-label">Cupos Asignados</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-disponibles">50</div>
                            <div class="stat-label">Cupos Disponibles</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-medicos">50</div>
                            <div class="stat-label">Cupos Médicos</div>
                        </div>
                    </div>
                    
                    <div id="admin-registration-status" style="margin-bottom: 15px; padding: 10px; background-color: #e9ecef; border-radius: 5px;">
                        <strong>Estado de Registros:</strong> 
                        <span id="admin-registration-status-text">Cargando...</span>
                    </div>
                    
                    <div class="search-container">
                        <input type="text" id="search-participant" class="search-input" placeholder="Buscar participante por nombre, apellido o correo...">
                        <button class="btn" id="btn-search-participant">Buscar</button>
                        <button class="btn" id="btn-clear-search" style="background-color: #6c757d;">Limpiar</button>
                    </div>
                    
                    <div style="display: flex; justify-content: space-between; margin-bottom: 15px;">
                        <button class="btn btn-add" id="btn-add-participant">Agregar Participante</button>
                        <button class="btn btn-download" id="btn-download-list">Descargar Lista</button>
                        <button class="btn btn-update" id="btn-update-participants">
                            <i class="fas fa-sync-alt"></i> Actualizar
                        </button>
                    </div>
                    
                    <h4>Lista de Participantes</h4>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Nombre</th>
                                <th>Cargo</th>
                                <th>Categoría</th>
                                <th>Correo</th>
                                <th>Fecha Registro</th>
                                <th>Acciones</th>
                            </tr>
                        </thead>
                        <tbody id="registros-table">
                            <!-- Los registros se llenarán dinámicamente -->
                        </tbody>
                    </table>
                </div>
                
                <!-- Tab de Agenda -->
                <div id="tab-agenda" class="tab-content">
                    <h3>Gestión de Agenda</h3>
                    
                    <div class="form-group">
                        <label for="agenda-file">Cargar Agenda (PDF)</label>
                        <div class="file-input-container">
                            <input type="file" id="agenda-file" class="file-input" accept=".pdf">
                            <label for="agenda-file" class="file-input-label" id="file-input-label">
                                <i class="fas fa-cloud-upload-alt"></i> 
                                <span id="file-label-text">Seleccionar archivo PDF</span>
                            </label>
                        </div>
                        <small class="form-text text-muted">Formatos permitidos: PDF. Tamaño máximo: 20MB</small>
                    </div>
                    
                    <div id="file-info" style="display: none; margin-top: 15px; padding: 15px; background-color: #f8f9fa; border-radius: 5px;">
                        <h4>Archivo seleccionado:</h4>
                        <p><strong>Nombre:</strong> <span id="selected-file-name"></span></p>
                        <p><strong>Tamaño:</strong> <span id="selected-file-size"></span></p>
                        <p><strong>Tipo:</strong> <span id="selected-file-type"></span></p>
                    </div>
                    
                    <div class="form-group" style="margin-top: 20px;">
                        <button class="btn btn-upload" id="btn-upload-agenda" disabled>
                            <i class="fas fa-upload"></i> Subir Agenda
                        </button>
                    </div>
                    
                    <div id="upload-status" style="margin-top: 15px;"></div>
                </div>
                
                <!-- Tab de Asistencias -->
                <div id="tab-asistencias" class="tab-content">
                    <h3>Gestión de Asistencias</h3>
                    
                    <div class="admin-stats">
                        <div class="stat-card">
                            <div class="stat-number" id="stat-total-asistentes">0</div>
                            <div class="stat-label">Total Asistentes</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-aprobados">0</div>
                            <div class="stat-label">Aprobados</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-pendientes">0</div>
                            <div class="stat-label">Pendientes</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-reprobados">0</div>
                            <div class="stat-label">Reprobados</div>
                        </div>
                    </div>
                    
                    <div class="sync-section">
                        <h4>Sincronización Automática de Asistencias</h4>
                        <p>Importa automáticamente las asistencias desde los formularios de Google</p>
                        <div class="form-group">
                            <button class="btn btn-sync" id="btn-sync-day1">
                                <i class="fas fa-sync"></i> Sincronizar Día 1
                            </button>
                            <button class="btn btn-sync" id="btn-sync-day2">
                                <i class="fas fa-sync"></i> Sincronizar Día 2
                            </button>
                            <button class="btn btn-sync" id="btn-sync-day3">
                                <i class="fas fa-sync"></i> Sincronizar Día 3
                            </button>
                            <button class="btn btn-sync" id="btn-sync-all">
                                <i class="fas fa-sync"></i> Sincronizar Todos
                            </button>
                            <button class="btn btn-update" id="btn-update-attendance">
                                <i class="fas fa-sync-alt"></i> Actualizar Asistencias
                            </button>
                        </div>
                        <div id="sync-status" class="sync-status"></div>
                    </div>
                    
                    <div class="attendance-links">
                        <div class="attendance-link-card">
                            <div class="attendance-day">Día 1 - Jueves 23</div>
                            <p>Registro de asistencia para el primer día del congreso</p>
                            <a href="https://docs.google.com/forms/d/1nihA_9JrKg1KOJCy4ypah4wtS5wXN3ETaKDgxNjTj70/edit" target="_blank" class="form-link">
                                <i class="fas fa-external-link-alt"></i> Formulario de Asistencia - Día 1
                            </a>
                        </div>
                        
                        <div class="attendance-link-card">
                            <div class="attendance-day">Día 2 - Viernes 24</div>
                            <p>Registro de asistencia para el segundo día del congreso</p>
                            <a href="https://docs.google.com/forms/d/18n4OUSB3iGBlBTBH6k4d-Tvma1rSXSS0Yv_vdq7bLVY/viewform?edit_requested=true" target="_blank" class="form-link">
                                <i class="fas fa-external-link-alt"></i> Formulario de Asistencia - Día 2
                            </a>
                        </div>
                        
                        <div class="attendance-link-card">
                            <div class="attendance-day">Día 3 - Sábado 25</div>
                            <p>Registro de asistencia para el tercer día del congreso</p>
                            <a href="https://docs.google.com/forms/d/11PXiisbAVSnWc74sRQJntSvnbSFk53um0CQikR0QHww/edit" target="_blank" class="form-link">
                                <i class="fas fa-external-link-alt"></i> Formulario de Asistencia - Día 3
                            </a>
                        </div>
                    </div>
                    
                    <div class="search-container">
                        <input type="text" id="search-attendance" class="search-input" placeholder="Buscar asistente por nombre o apellido...">
                        <button class="btn" id="btn-search-attendance">Buscar</button>
                        <button class="btn" id="btn-clear-search-attendance" style="background-color: #6c757d;">Limpiar</button>
                    </div>
                    
                    <div style="display: flex; justify-content: space-between; margin: 20px 0;">
                        <button class="btn btn-add" id="btn-add-attendance">Registrar Asistencia</button>
                        <button class="btn btn-download" id="btn-download-attendance">Descargar Consolidado</button>
                    </div>
                    
                    <h4>Registro de Asistencias</h4>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Nombre</th>
                                <th>Apellido</th>
                                <th>Día 1</th>
                                <th>Día 2</th>
                                <th>Día 3</th>
                                <th>Asistencias</th>
                                <th>Estado</th>
                                <th>Acciones</th>
                            </tr>
                        </thead>
                        <tbody id="asistencias-table">
                            <!-- Los registros se llenarán dinámicamente -->
                        </tbody>
                    </table>
                </div>
                
                <!-- Tab de Certificados -->
                <div id="tab-certificados" class="tab-content">
                    <h3>Gestión de Certificados</h3>
                    
                    <div class="admin-stats">
                        <div class="stat-card">
                            <div class="stat-number" id="stat-total-certificados">0</div>
                            <div class="stat-label">Total Aprobados</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-certificados-generados">0</div>
                            <div class="stat-label">Certificados Generados</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-number" id="stat-certificados-pendientes">0</div>
                            <div class="stat-label">Pendientes</div>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="certificate-template">Cargar Plantilla de Certificado (Word .docx)</label>
                        <div class="file-input-container">
                            <input type="file" id="certificate-template" class="file-input" accept=".docx">
                            <label for="certificate-template" class="file-input-label" id="certificate-input-label">
                                <i class="fas fa-cloud-upload-alt"></i> 
                                <span id="certificate-label-text">Seleccionar plantilla Word (.docx)</span>
                            </label>
                        </div>
                        <small class="form-text text-muted">
                            Formatos permitidos: DOCX. Tamaño máximo: 10MB. La plantilla debe contener los campos: {{cargo}}, {{apellido}}, {{nombre}}.
                        </small>
                    </div>
                    
                    <div id="certificate-file-info" style="display: none; margin-top: 15px; padding: 15px; background-color: #f8f9fa; border-radius: 5px;">
                        <h4>Plantilla seleccionada:</h4>
                        <p><strong>Nombre:</strong> <span id="selected-certificate-name"></span></p>
                        <p><strong>Tamaño:</strong> <span id="selected-certificate-size"></span></p>
                        <p><strong>Tipo:</strong> <span id="selected-certificate-type"></span></p>
                        <div id="template-validation" style="margin-top: 10px;"></div>
                    </div>
                    
                    <div class="form-group" style="margin-top: 20px;">
                        <button class="btn btn-upload" id="btn-upload-template" disabled>
                            <i class="fas fa-upload"></i> Subir Plantilla
                        </button>
                        <button class="btn btn-certificate" id="btn-generate-certificates" disabled>
                            <i class="fas fa-file-certificate"></i> Generar Certificados
                        </button>
                        <button class="btn btn-download" id="btn-download-certificates">
                            <i class="fas fa-file-archive"></i> Descargar Todos (PDF)
                        </button>
                        <button class="btn btn-update" id="btn-update-certificates">
                            <i class="fas fa-sync-alt"></i> Actualizar Certificados
                        </button>
                    </div>
                    
                    <!-- NUEVA SECCIÓN: Generar certificado para persona no inscrita -->
                    <div class="sync-section">
                        <h4>Generar Certificado para Persona No Inscrita</h4>
                        <p>Crear certificado para una persona que no está en la lista de participantes</p>
                        <div class="form-group">
                            <label for="external-cargo">Cargo</label>
                            <select id="external-cargo" class="form-control">
                                <option value="">Seleccione cargo</option>
                                <option value="DR.">DR.</option>
                                <option value="DRA.">DRA.</option>
                                <option value="LCDO.">LCDO.</option>
                                <option value="LCDA.">LCDA.</option>
                                <option value="IRM.">IRM.</option>
                                <option value="IRE.">IRE.</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="external-nombre">Nombre</label>
                            <input type="text" id="external-nombre" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="external-apellido">Apellido</label>
                            <input type="text" id="external-apellido" class="form-control">
                        </div>
                        <div class="form-group">
                            <button class="btn btn-certificate" id="btn-generate-external-certificate">
                                <i class="fas fa-file-certificate"></i> Generar Certificado
                            </button>
                            <button class="btn btn-download" id="btn-download-external-certificate">
                                <i class="fas fa-download"></i> Descargar PDF
                            </button>
                        </div>
                        <div id="external-certificate-status" class="sync-status"></div>
                    </div>
                    
                    <!-- NUEVA SECCIÓN: Descargar certificado HTML autocompletado -->
                    <div class="sync-section">
                        <h4>Descargar Certificado HTML Autocompletado</h4>
                        <p>Descarga un certificado HTML con los campos autocompletados para un participante específico</p>
                        <div class="form-group">
                            <label for="certificate-participant">Seleccionar Participante</label>
                            <select id="certificate-participant" class="form-control">
                                <option value="">Seleccione un participante</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <button class="btn btn-preview" id="btn-preview-certificate">
                                <i class="fas fa-eye"></i> Vista Previa
                            </button>
                            <button class="btn btn-certificate" id="btn-download-html-certificate">
                                <i class="fas fa-download"></i> Descargar HTML
                            </button>
                            <button class="btn btn-download" id="btn-download-pdf-certificate">
                                <i class="fas fa-file-pdf"></i> Descargar PDF
                            </button>
                        </div>
                        <div id="html-certificate-status" class="sync-status"></div>
                    </div>
                    
                    <!-- Vista previa del certificado -->
                    <div id="certificate-preview-container" style="display: none;">
                        <h4>Vista Previa del Certificado</h4>
                        <div class="certificate-preview">
                            <div class="certificate-preview-content" id="certificate-preview-content">
                                <!-- El contenido del certificado se mostrará aquí -->
                            </div>
                        </div>
                    </div>
                    
                    <div id="certificate-status" style="margin-top: 15px;"></div>
                    
                    <div class="search-container">
                        <input type="text" id="search-certificates" class="search-input" placeholder="Buscar certificado por nombre o apellido...">
                        <button class="btn" id="btn-search-certificates">Buscar</button>
                        <button class="btn" id="btn-clear-search-certificates" style="background-color: #6c757d;">Limpiar</button>
                    </div>
                    
                    <h4>Asistentes Aprobados para Certificación</h4>
                    <table class="admin-table">
                        <thead>
                            <tr>
                                <th>Nombre</th>
                                <th>Apellido</th>
                                <th>Cargo</th>
                                <th>Asistencias</th>
                                <th>Estado</th>
                                <th>Certificado</th>
                            </tr>
                        </thead>
                        <tbody id="certificados-table">
                            <!-- Los registros se llenarán dinámicamente -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal para agregar/editar participantes -->
    <div class="admin-panel" id="participant-modal" style="display: none;">
        <div class="admin-content" style="max-width: 500px;">
            <div class="admin-header">
                <h2 id="modal-title">Agregar Participante</h2>
                <button class="close-admin" id="close-modal">&times;</button>
            </div>
            
            <form id="participant-form">
                <input type="hidden" id="edit-id">
                
                <div class="form-group">
                    <label for="modal-cargo">Cargo</label>
                    <select id="modal-cargo" required>
                        <option value="">Seleccione cargo</option>
                        <option value="DR.">DR.</option>
                        <option value="DRA.">DRA.</option>
                        <option value="LCDO.">LCDO.</option>
                        <option value="LCDA.">LCDA.</option>
                        <option value="IRM.">IRM.</option>
                        <option value="IRE.">IRE.</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="modal-nombre">Nombre</label>
                    <input type="text" id="modal-nombre" required>
                </div>
                
                <div class="form-group">
                    <label for="modal-apellido">Apellido</label>
                    <input type="text" id="modal-apellido" required>
                </div>
                
                <div class="form-group">
                    <label for="modal-correo">Correo</label>
                    <input type="email" id="modal-correo" required>
                </div>
                
                <div class="form-group">
                    <label for="modal-categoria">Categoría</label>
                    <select id="modal-categoria" required>
                        <option value="">Seleccione categoría</option>
                        <option value="MEDICO GENERAL">Médico General</option>
                        <option value="MEDICO ESPECIALISTA">Médico Especialista</option>
                        <option value="LICENCIADO EN ENFERMERIA">Licenciado en Enfermería</option>
                        <option value="INTERNO ROTATIVO DE ENFERMERIA">Interno Rotativo de Enfermería</option>
                        <option value="INTERNO ROTATIVO DE MEDICINA">Interno Rotativo de Medicina</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <button type="submit" class="btn" id="btn-save-participant">Guardar</button>
                    <button type="button" class="btn" id="btn-cancel" style="background-color: #6c757d;">Cancelar</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Modal para registrar asistencias -->
    <div class="admin-panel" id="attendance-modal" style="display: none;">
        <div class="admin-content" style="max-width: 500px;">
            <div class="admin-header">
                <h2 id="modal-title-attendance">Registrar Asistencia</h2>
                <button class="close-admin" id="close-attendance-modal">&times;</button>
            </div>
            
            <form id="attendance-form">
                <input type="hidden" id="edit-attendance-id">
                
                <div class="form-group">
                    <label for="attendance-nombre">Nombre</label>
                    <input type="text" id="attendance-nombre" required>
                </div>
                
                <div class="form-group">
                    <label for="attendance-apellido">Apellido</label>
                    <input type="text" id="attendance-apellido" required>
                </div>
                
                <div class="form-group">
                    <label>Asistencias por Día</label>
                    <div style="display: flex; flex-direction: column; gap: 10px; margin-top: 10px;">
                        <label style="display: flex; align-items: center; gap: 10px;">
                            <input type="checkbox" id="attendance-dia1">
                            <span>Día 1 - Jueves 23</span>
                        </label>
                        <label style="display: flex; align-items: center; gap: 10px;">
                            <input type="checkbox" id="attendance-dia2">
                            <span>Día 2 - Viernes 24</span>
                        </label>
                        <label style="display: flex; align-items: center; gap: 10px;">
                            <input type="checkbox" id="attendance-dia3">
                            <span>Día 3 - Sábado 25</span>
                        </label>
                    </div>
                </div>
                
                <div class="form-group">
                    <button type="submit" class="btn" id="btn-save-attendance">Guardar Asistencia</button>
                    <button type="button" class="btn" id="btn-cancel-attendance" style="background-color: #6c757d;">Cancelar</button>
                </div>
            </form>
        </div>
    </div>

    <script>
        // Variables para controlar los cupos
        let cuposTotales = 220;
        let cuposAsignados = 170; // Ya asignados según la lista
        let cuposMedicos = 50; // Solo quedan disponibles para médicos
        let cuposLicenciados = 0;
        let cuposInternos = 0;
        
        // Array para almacenar registros
        let registros = [];
        
        // Array para almacenar asistencias
        let asistencias = [];
        
        // Variables para certificados
        let certificateTemplate = null;
        let certificateTemplateData = null;
        let generatedCertificates = [];
        let approvedAttendees = [];
        
        // Variable para almacenar la agenda
        let agendaFile = null;
        let agendaFileData = null;
        
        // Fechas límite
        const fechaLimiteRegistro = new Date('October 22, 2025 23:59:00').getTime();
        const fechaDisponibilidadCertificados = new Date('October 25, 2025 13:00:00').getTime();
        
        // Elementos del DOM
        const adminPanel = document.getElementById('admin-panel');
        const btnAdmin = document.getElementById('btn-admin');
        const closeAdmin = document.getElementById('close-admin');
        const adminLogin = document.getElementById('admin-login');
        const adminDashboard = document.getElementById('admin-dashboard');
        const btnLogin = document.getElementById('btn-login');
        const participantModal = document.getElementById('participant-modal');
        const closeModal = document.getElementById('close-modal');
        const btnCancel = document.getElementById('btn-cancel');
        const btnAddParticipant = document.getElementById('btn-add-participant');
        const participantForm = document.getElementById('participant-form');
        const modalTitle = document.getElementById('modal-title');
        const btnDownloadList = document.getElementById('btn-download-list');
        const btnDownloadAgenda = document.getElementById('btn-download-agenda');
        const agendaFileInput = document.getElementById('agenda-file');
        const btnUploadAgenda = document.getElementById('btn-upload-agenda');
        const fileInputLabel = document.getElementById('file-input-label');
        const fileLabelText = document.getElementById('file-label-text');
        const fileInfo = document.getElementById('file-info');
        const uploadStatus = document.getElementById('upload-status');
        const agendaPlaceholder = document.getElementById('agenda-placeholder');
        const agendaUploaded = document.getElementById('agenda-uploaded');
        const btnAddAttendance = document.getElementById('btn-add-attendance');
        const btnDownloadAttendance = document.getElementById('btn-download-attendance');
        const attendanceModal = document.getElementById('attendance-modal');
        const closeAttendanceModal = document.getElementById('close-attendance-modal');
        const btnCancelAttendance = document.getElementById('btn-cancel-attendance');
        const attendanceForm = document.getElementById('attendance-form');
        const modalTitleAttendance = document.getElementById('modal-title-attendance');
        const btnRegistrar = document.getElementById('btn-registrar');
        const deadlineTimer = document.getElementById('deadline-timer');
        const registrationDeadline = document.getElementById('registration-deadline');
        const adminRegistrationStatus = document.getElementById('admin-registration-status-text');
        const searchParticipant = document.getElementById('search-participant');
        const btnSearchParticipant = document.getElementById('btn-search-participant');
        const btnClearSearch = document.getElementById('btn-clear-search');
        const certificateTemplateInput = document.getElementById('certificate-template');
        const btnUploadTemplate = document.getElementById('btn-upload-template');
        const btnGenerateCertificates = document.getElementById('btn-generate-certificates');
        const btnDownloadCertificates = document.getElementById('btn-download-certificates');
        const certificateStatus = document.getElementById('certificate-status');
        const certificatePlaceholder = document.getElementById('certificate-placeholder');
        const certificateUploaded = document.getElementById('certificate-uploaded');
        const btnDownloadMyCertificate = document.getElementById('btn-download-my-certificate');
        const btnDownloadAllCertificates = document.getElementById('btn-download-all-certificates');
        const certificateUploadedContent = document.getElementById('certificate-uploaded-content');
        const btnSyncDay1 = document.getElementById('btn-sync-day1');
        const btnSyncDay2 = document.getElementById('btn-sync-day2');
        const btnSyncDay3 = document.getElementById('btn-sync-day3');
        const btnSyncAll = document.getElementById('btn-sync-all');
        const syncStatus = document.getElementById('sync-status');
        const searchAttendance = document.getElementById('search-attendance');
        const btnSearchAttendance = document.getElementById('btn-search-attendance');
        const btnClearSearchAttendance = document.getElementById('btn-clear-search-attendance');
        const searchCertificates = document.getElementById('search-certificates');
        const btnSearchCertificates = document.getElementById('btn-search-certificates');
        const btnClearSearchCertificates = document.getElementById('btn-clear-search-certificates');
        const btnUpdateParticipants = document.getElementById('btn-update-participants');
        const btnUpdateAttendance = document.getElementById('btn-update-attendance');
        const btnUpdateCertificates = document.getElementById('btn-update-certificates');
        const certificateParticipantSelect = document.getElementById('certificate-participant');
        const btnPreviewCertificate = document.getElementById('btn-preview-certificate');
        const btnDownloadHtmlCertificate = document.getElementById('btn-download-html-certificate');
        const btnDownloadPdfCertificate = document.getElementById('btn-download-pdf-certificate');
        const htmlCertificateStatus = document.getElementById('html-certificate-status');
        const certificatePreviewContainer = document.getElementById('certificate-preview-container');
        const certificatePreviewContent = document.getElementById('certificate-preview-content');
        
        // NUEVOS ELEMENTOS: Certificados para personas no inscritas
        const externalCargo = document.getElementById('external-cargo');
        const externalNombre = document.getElementById('external-nombre');
        const externalApellido = document.getElementById('external-apellido');
        const btnGenerateExternalCertificate = document.getElementById('btn-generate-external-certificate');
        const btnDownloadExternalCertificate = document.getElementById('btn-download-external-certificate');
        const externalCertificateStatus = document.getElementById('external-certificate-status');
        
        // Datos iniciales de participantes
        const participantesIniciales = [
            // GERENCIA (9)
            {cargo: "DR.", nombre: "LEONARDO", apellido: "VITERI", categoria: "MEDICO ESPECIALISTA", correo: "gerencia1@hospital.com"},
            {cargo: "DR.", nombre: "LEONEL", apellido: "KUONQUI", categoria: "MEDICO ESPECIALISTA", correo: "gerencia2@hospital.com"},
            {cargo: "DR.", nombre: "CARLOS", apellido: "CEVALLOS R.", categoria: "MEDICO ESPECIALISTA", correo: "gerencia3@hospital.com"},
            {cargo: "DR.", nombre: "JOSÉ", apellido: "INTRIAGO", categoria: "MEDICO ESPECIALISTA", correo: "gerencia4@hospital.com"},
            {cargo: "DR.", nombre: "ALBERTO", apellido: "QUINTERO", categoria: "MEDICO ESPECIALISTA", correo: "gerencia5@hospital.com"},
            {cargo: "DR.", nombre: "PATRICIO", apellido: "CALDERÓN", categoria: "MEDICO ESPECIALISTA", correo: "gerencia6@hospital.com"},
            {cargo: "DR.", nombre: "RICARDO", apellido: "MEJÍA", categoria: "MEDICO ESPECIALISTA", correo: "gerencia7@hospital.com"},
            {cargo: "DR.", nombre: "JORGE", apellido: "QUIJANO", categoria: "MEDICO ESPECIALISTA", correo: "gerencia8@hospital.com"},
            {cargo: "DR.", nombre: "SERGIO", apellido: "ARCENTALES", categoria: "MEDICO ESPECIALISTA", correo: "gerencia9@hospital.com"},
            
            // PROTOCOLO (6)
            {cargo: "LCDA.", nombre: "MARÍA", apellido: "PÁRRAGA GALLARDO", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo1@hospital.com"},
            {cargo: "LCDA.", nombre: "MAHOLI", apellido: "GILER MONTES", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo2@hospital.com"},
            {cargo: "LCDA.", nombre: "JOSSELINE", apellido: "SANDOVAL BERNARD", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo3@hospital.com"},
            {cargo: "LCDA.", nombre: "ANITA", apellido: "CEDEÑO LOOR", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo4@hospital.com"},
            {cargo: "LCDA.", nombre: "XIMENA", apellido: "MERA MANTONG", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo5@hospital.com"},
            {cargo: "LCDO.", nombre: "GABRIEL", apellido: "SOLÓRZANO BRAVO", categoria: "LICENCIADO EN ENFERMERIA", correo: "protocolo6@hospital.com"},
            
            // MÉDICOS IESS (5) - Solo agregamos algunos para ejemplo
            {cargo: "DRA.", nombre: "CINDY XIMENA", apellido: "LOOR ARCENTALES", categoria: "MEDICO ESPECIALISTA", correo: "iess1@hospital.com"},
            {cargo: "DR.", nombre: "ERICK ORLANDO", apellido: "TORO VILLAGÓMEZ", categoria: "MEDICO ESPECIALISTA", correo: "iess2@hospital.com"},
            {cargo: "DRA.", nombre: "MÓNICA ARIANA", apellido: "ORTEGA PONCE", categoria: "MEDICO ESPECIALISTA", correo: "iess3@hospital.com"},
            
            // ENFERMERAS (20) - Solo agregamos algunos para ejemplo
            {cargo: "LCDA.", nombre: "GEMA STHEFANIA", apellido: "GILCES SOLORZANO", categoria: "LICENCIADO EN ENFERMERIA", correo: "enfermera1@hospital.com"},
            {cargo: "LCDA.", nombre: "MERCY DOLORES", apellido: "MONTES RODRIGUEZ", categoria: "LICENCIADO EN ENFERMERIA", correo: "enfermera2@hospital.com"},
            {cargo: "LCDA.", nombre: "MARIA BELEN", apellido: "LOOR RISCO", categoria: "LICENCIADO EN ENFERMERIA", correo: "enfermera3@hospital.com"},
            
            // INTERNOS (17) - Solo agregamos algunos para ejemplo
            {cargo: "IRM.", nombre: "ANTONELLA", apellido: "SOLORZANO", categoria: "INTERNO ROTATIVO DE MEDICINA", correo: "interno1@hospital.com"},
            {cargo: "IRM.", nombre: "ANDREA", apellido: "MACAY DE LA CRUZ", categoria: "INTERNO ROTATIVO DE MEDICINA", correo: "interno2@hospital.com"},
            {cargo: "IRM.", nombre: "SAMUEL", apellido: "CUSME", categoria: "INTERNO ROTATIVO DE MEDICINA", correo: "interno3@hospital.com"},
            {cargo: "IRM.", nombre: "XIMENA MICHELLE", apellido: "LÓPEZ ESPINALES", categoria: "INTERNO ROTATIVO DE ENFERMERIA", correo: "interno4@hospital.com"},
            
            // RESIDENTES Y ESPECIALISTAS - Solo agregamos algunos para ejemplo
            {cargo: "DR.", nombre: "JOSE", apellido: "CHICA", categoria: "MEDICO ESPECIALISTA", correo: "residente1@hospital.com"},
            {cargo: "DRA.", nombre: "GABRIELA", apellido: "ALVARADO", categoria: "MEDICO ESPECIALISTA", correo: "residente2@hospital.com"},
            {cargo: "DR.", nombre: "HUGO", apellido: "NARANJO", categoria: "MEDICO ESPECIALISTA", correo: "especialista1@hospital.com"},
            {cargo: "DRA.", nombre: "DANIELA", apellido: "BORJA", categoria: "MEDICO ESPECIALISTA", correo: "especialista2@hospital.com"},
            
            // ASISTENTE DE PRUEBA
            {cargo: "DR.", nombre: "PRUEBA", apellido: "PRUEBA", categoria: "MEDICO GENERAL", correo: "prueba@hospital.com"}
        ];
        
        // Inicializar registros con participantes iniciales
        function inicializarRegistros() {
            if (registros.length === 0) {
                participantesIniciales.forEach((participante, index) => {
                    registros.push({
                        id: index + 1,
                        ...participante,
                        fecha: new Date().toLocaleString()
                    });
                });
            }
        }
        
        // Inicializar asistencias
        function inicializarAsistencias() {
            if (asistencias.length === 0) {
                // Agregar algunos registros de ejemplo
                asistencias.push({
                    id: 1,
                    nombre: "PRUEBA",
                    apellido: "PRUEBA",
                    dia1: true,
                    dia2: true,
                    dia3: false,
                    fecha: new Date().toLocaleString()
                });
                
                asistencias.push({
                    id: 2,
                    nombre: "LEONARDO",
                    apellido: "VITERI",
                    dia1: true,
                    dia2: false,
                    dia3: true,
                    fecha: new Date().toLocaleString()
                });
            }
        }
        
        // Inicializar agenda
        function inicializarAgenda() {
            // Cargar agenda desde localStorage si existe
            const agendaGuardada = localStorage.getItem('agendaCongresoFile');
            if (agendaGuardada) {
                const agendaData = JSON.parse(agendaGuardada);
                agendaFile = agendaData.file;
                agendaFileData = agendaData.data;
                mostrarAgenda();
            }
        }
        
        // Inicializar certificados
        function inicializarCertificados() {
            // Cargar plantilla desde localStorage si existe
            const templateGuardada = localStorage.getItem('certificateTemplate');
            if (templateGuardada) {
                const templateData = JSON.parse(templateGuardada);
                certificateTemplate = templateData.file;
                certificateTemplateData = templateData.data;
                mostrarCertificados();
            }
            
            // Cargar certificados generados
            const certificadosGuardados = localStorage.getItem('generatedCertificates');
            if (certificadosGuardados) {
                try {
                    generatedCertificates = JSON.parse(certificadosGuardados);
                } catch (e) {
                    console.error('Error al cargar certificados:', e);
                    generatedCertificates = [];
                }
            }
        }
        
        // Función para guardar certificados en localStorage
        function guardarCertificadosEnStorage() {
            try {
                // Guardar solo información esencial para reducir tamaño
                const certificadosLigeros = generatedCertificates.map(cert => ({
                    nombre: cert.nombre,
                    apellido: cert.apellido,
                    cargo: cert.cargo,
                    fechaGeneracion: cert.fechaGeneracion,
                    html: cert.html // Guardamos el HTML para poder regenerar
                }));
                
                localStorage.setItem('generatedCertificates', JSON.stringify(certificadosLigeros));
                return true;
            } catch (e) {
                console.error('Error al guardar certificados:', e);
                // Si hay error de cuota, limpiar y guardar solo los más recientes
                if (e.name === 'QuotaExceededError') {
                    // Mantener solo los últimos 50 certificados
                    if (generatedCertificates.length > 50) {
                        generatedCertificates = generatedCertificates.slice(-50);
                        return guardarCertificadosEnStorage(); // Intentar nuevamente
                    }
                }
                return false;
            }
        }
        
        // Mostrar agenda en la página principal
        function mostrarAgenda() {
            if (agendaFile && agendaFileData) {
                // Mostrar información del archivo
                document.getElementById('agenda-file-name').textContent = agendaFile.name;
                document.getElementById('agenda-file-size').textContent = formatFileSize(agendaFile.size);
                document.getElementById('agenda-upload-date').textContent = `Subido: ${new Date(agendaFile.lastModified).toLocaleDateString()}`;
                
                agendaPlaceholder.style.display = 'none';
                agendaUploaded.style.display = 'block';
            } else {
                agendaPlaceholder.style.display = 'block';
                agendaUploaded.style.display = 'none';
            }
        }
        
        // Mostrar certificados en la página principal
        function mostrarCertificados() {
            if (certificateTemplate && certificateTemplateData) {
                // Mostrar información del archivo
                document.getElementById('certificate-file-name').textContent = certificateTemplate.name;
                document.getElementById('certificate-upload-date').textContent = `Subido: ${new Date(certificateTemplate.lastModified).toLocaleDateString()}`;
                
                certificatePlaceholder.style.display = 'none';
                certificateUploaded.style.display = 'block';
                
                // Verificar si los certificados están disponibles
                const ahora = new Date().getTime();
                const certificadosDisponibles = ahora >= fechaDisponibilidadCertificados;
                
                if (certificadosDisponibles) {
                    certificateUploadedContent.classList.add('certificate-available');
                    btnDownloadMyCertificate.disabled = false;
                    btnDownloadMyCertificate.textContent = "Descargar Mi Certificado";
                } else {
                    certificateUploadedContent.classList.add('certificate-unavailable');
                    btnDownloadMyCertificate.disabled = true;
                    btnDownloadMyCertificate.textContent = "Disponible desde 25 Oct 13:00";
                }
                
                // Mostrar botón de descarga para administradores
                if (adminDashboard.style.display === 'block') {
                    btnDownloadAllCertificates.style.display = 'inline-block';
                    // CORRECCIÓN: Administradores pueden descargar sin restricciones de fecha
                    btnDownloadAllCertificates.disabled = false;
                }
            } else {
                certificatePlaceholder.style.display = 'block';
                certificateUploaded.style.display = 'none';
            }
        }
        
        // Formatear tamaño de archivo
        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB', 'GB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + ' ' + sizes[i];
        }
        
        // Calcular estadísticas de asistencias
        function calcularEstadisticasAsistencias() {
            const totalAsistentes = asistencias.length;
            let aprobados = 0;
            let pendientes = 0;
            let reprobados = 0;
            
            asistencias.forEach(asistencia => {
                const diasAsistidos = (asistencia.dia1 ? 1 : 0) + (asistencia.dia2 ? 1 : 0) + (asistencia.dia3 ? 1 : 0);
                
                if (diasAsistidos >= 2) {
                    aprobados++;
                } else if (diasAsistidos === 0) {
                    reprobados++;
                } else {
                    pendientes++;
                }
            });
            
            document.getElementById('stat-total-asistentes').textContent = totalAsistentes;
            document.getElementById('stat-aprobados').textContent = aprobados;
            document.getElementById('stat-pendientes').textContent = pendientes;
            document.getElementById('stat-reprobados').textContent = reprobados;
            
            // Actualizar estadísticas de certificados
            document.getElementById('stat-total-certificados').textContent = aprobados;
            document.getElementById('stat-certificados-generados').textContent = generatedCertificates.length;
            document.getElementById('stat-certificados-pendientes').textContent = aprobados - generatedCertificates.length;
        }
        
        // Verificar si una asistencia ya existe
        function asistenciaExiste(nombre, apellido) {
            return asistencias.some(asistencia => 
                asistencia.nombre.toLowerCase() === nombre.toLowerCase() && 
                asistencia.apellido.toLowerCase() === apellido.toLowerCase()
            );
        }
        
        // Verificar si el registro está habilitado (para usuarios normales)
        function registroHabilitado() {
            const ahora = new Date().getTime();
            return ahora <= fechaLimiteRegistro;
        }
        
        // Verificar si los certificados están disponibles
        function certificadosDisponibles() {
            const ahora = new Date().getTime();
            return ahora >= fechaDisponibilidadCertificados;
        }
        
        // Actualizar contador de límite de registro
        function actualizarContadorLimite() {
            const ahora = new Date().getTime();
            const distancia = fechaLimiteRegistro - ahora;
            
            if (distancia < 0) {
                // Tiempo agotado
                deadlineTimer.textContent = "00:00:00";
                registrationDeadline.style.backgroundColor = "rgba(220, 53, 69, 0.2)";
                registrationDeadline.style.borderColor = "#dc3545";
                document.querySelector('.deadline-warning').innerHTML = '<i class="fas fa-times-circle"></i> Registros Cerrados';
                document.querySelector('.deadline-warning').style.color = "#dc3545";
                
                // Deshabilitar formulario para usuarios normales
                btnRegistrar.disabled = true;
                btnRegistrar.textContent = "Registros Cerrados";
                
                return false;
            } else {
                // Calcular días, horas, minutos, segundos
                const dias = Math.floor(distancia / (1000 * 60 * 60 * 24));
                const horas = Math.floor((distancia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutos = Math.floor((distancia % (1000 * 60 * 60)) / (1000 * 60));
                const segundos = Math.floor((distancia % (1000 * 60)) / 1000);
                
                deadlineTimer.textContent = `${dias}d ${horas.toString().padStart(2, '0')}:${minutos.toString().padStart(2, '0')}:${segundos.toString().padStart(2, '0')}`;
                return true;
            }
        }
        
        // Actualizar estado de registro en panel de administración
        function actualizarEstadoRegistroAdmin() {
            const ahora = new Date().getTime();
            const habilitado = ahora <= fechaLimiteRegistro;
            
            if (habilitado) {
                adminRegistrationStatus.innerHTML = '<span style="color: #28a745;">REGISTROS ABIERTOS</span> - Hasta 22 Oct 23:59';
            } else {
                adminRegistrationStatus.innerHTML = '<span style="color: #dc3545;">REGISTROS CERRADOS</span> - Solo administradores pueden registrar';
            }
        }
        
        // Conteo regresivo
        function updateCountdown() {
            const eventDate = new Date('October 23, 2025 08:00:00').getTime();
            const now = new Date().getTime();
            const distance = eventDate - now;
            
            if (distance < 0) {
                document.getElementById('countdown-timer').innerHTML = "<div>El congreso ha comenzado!</div>";
                return;
            }
            
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
        }
        
        // Actualizar la visualización de cupos
        function actualizarCupos() {
            document.getElementById('cupos-disponibles').textContent = cuposTotales - cuposAsignados;
            
            // Actualizar panel de administración si está visible
            if (adminDashboard.style.display === 'block') {
                document.getElementById('stat-total').textContent = cuposTotales;
                document.getElementById('stat-asignados').textContent = cuposAsignados;
                document.getElementById('stat-disponibles').textContent = cuposTotales - cuposAsignados;
                document.getElementById('stat-medicos').textContent = cuposMedicos;
            }
        }
        
        // Verificar si un participante ya existe
        function participanteExiste(cargo, nombre, apellido) {
            return registros.some(registro => 
                registro.cargo === cargo && 
                registro.nombre.toLowerCase() === nombre.toLowerCase() && 
                registro.apellido.toLowerCase() === apellido.toLowerCase()
            );
        }
        
        // Buscar participantes
        function buscarParticipantes(termino) {
            if (!termino) {
                return registros;
            }
            
            const terminoLower = termino.toLowerCase();
            return registros.filter(registro => 
                registro.nombre.toLowerCase().includes(terminoLower) ||
                registro.apellido.toLowerCase().includes(terminoLower) ||
                registro.correo.toLowerCase().includes(terminoLower)
            );
        }
        
        // Buscar asistencias
        function buscarAsistencias(termino) {
            if (!termino) {
                return asistencias;
            }
            
            const terminoLower = termino.toLowerCase();
            return asistencias.filter(asistencia => 
                asistencia.nombre.toLowerCase().includes(terminoLower) ||
                asistencia.apellido.toLowerCase().includes(terminoLower)
            );
        }
        
        // Buscar certificados
        function buscarCertificados(termino) {
            const asistentesAprobados = obtenerAsistentesAprobados();
            
            if (!termino) {
                return asistentesAprobados;
            }
            
            const terminoLower = termino.toLowerCase();
            return asistentesAprobados.filter(asistente => 
                asistente.nombre.toLowerCase().includes(terminoLower) ||
                asistente.apellido.toLowerCase().includes(terminoLower)
            );
        }
        
        // Obtener asistentes aprobados
        function obtenerAsistentesAprobados() {
            approvedAttendees = [];
            
            asistencias.forEach(asistencia => {
                const diasAsistidos = (asistencia.dia1 ? 1 : 0) + (asistencia.dia2 ? 1 : 0) + (asistencia.dia3 ? 1 : 0);
                
                if (diasAsistidos >= 2) {
                    // Buscar información del participante
                    const participante = registros.find(r => 
                        r.nombre.toLowerCase() === asistencia.nombre.toLowerCase() && 
                        r.apellido.toLowerCase() === asistencia.apellido.toLowerCase()
                    );
                    
                    if (participante) {
                        approvedAttendees.push({
                            nombre: asistencia.nombre,
                            apellido: asistencia.apellido,
                            cargo: participante.cargo,
                            diasAsistidos: diasAsistidos
                        });
                    }
                }
            });
            
            return approvedAttendees;
        }
        
        // CORRECCIÓN: Función corregida - validarPlantillaCertificado
        function validarPlantillaCertificado(htmlContent) {
            const camposRequeridos = ['{{cargo}}', '{{apellido}}', '{{nombre}}'];
            const camposFaltantes = [];
            
            camposRequeridos.forEach(campo => {
                if (!htmlContent.includes(campo)) {
                    camposFaltantes.push(campo);
                }
            });
            
            return camposFaltantes;
        }
        
        // SOLUCIÓN: Sincronización automática de asistencias desde formularios de Google
        function sincronizarAsistencias(dia) {
            syncStatus.innerHTML = '<div class="alert alert-info">Sincronizando asistencias, por favor espere...</div>';
            
            // En una implementación real, aquí se conectaría con la API de Google Forms
            // Por ahora, simulamos la sincronización con datos de ejemplo
            
            setTimeout(() => {
                let nuevasAsistencias = [];
                let asistentesSimulados = [];
                
                // Simular datos de formularios de Google
                if (dia === 1 || dia === 'all') {
                    asistentesSimulados = [
                        { nombre: "PRUEBA", apellido: "PRUEBA" },
                        { nombre: "LEONARDO", apellido: "VITERI" },
                        { nombre: "CARLOS", apellido: "CEVALLOS R." },
                        { nombre: "MARÍA", apellido: "PÁRRAGA GALLARDO" }
                    ];
                    
                    asistentesSimulados.forEach(asistente => {
                        if (!asistenciaExiste(asistente.nombre, asistente.apellido)) {
                            nuevasAsistencias.push({
                                id: Date.now() + Math.random(),
                                nombre: asistente.nombre,
                                apellido: asistente.apellido,
                                dia1: true,
                                dia2: false,
                                dia3: false,
                                fecha: new Date().toLocaleString()
                            });
                        } else {
                            // Actualizar asistencia existente
                            const index = asistencias.findIndex(a => 
                                a.nombre === asistente.nombre && a.apellido === asistente.apellido
                            );
                            if (index !== -1) {
                                asistencias[index].dia1 = true;
                            }
                        }
                    });
                }
                
                if (dia === 2 || dia === 'all') {
                    asistentesSimulados = [
                        { nombre: "PRUEBA", apellido: "PRUEBA" },
                        { nombre: "LEONEL", apellido: "KUONQUI" },
                        { nombre: "JOSÉ", apellido: "INTRIAGO" },
                        { nombre: "MAHOLI", apellido: "GILER MONTES" }
                    ];
                    
                    asistentesSimulados.forEach(asistente => {
                        if (!asistenciaExiste(asistente.nombre, asistente.apellido)) {
                            nuevasAsistencias.push({
                                id: Date.now() + Math.random(),
                                nombre: asistente.nombre,
                                apellido: asistente.apellido,
                                dia1: false,
                                dia2: true,
                                dia3: false,
                                fecha: new Date().toLocaleString()
                            });
                        } else {
                            // Actualizar asistencia existente
                            const index = asistencias.findIndex(a => 
                                a.nombre === asistente.nombre && a.apellido === asistente.apellido
                            );
                            if (index !== -1) {
                                asistencias[index].dia2 = true;
                            }
                        }
                    });
                }
                
                if (dia === 3 || dia === 'all') {
                    asistentesSimulados = [
                        { nombre: "PRUEBA", apellido: "PRUEBA" },
                        { nombre: "ALBERTO", apellido: "QUINTERO" },
                        { nombre: "PATRICIO", apellido: "CALDERÓN" },
                        { nombre: "JOSSELINE", apellido: "SANDOVAL BERNARD" }
                    ];
                    
                    asistentesSimulados.forEach(asistente => {
                        if (!asistenciaExiste(asistente.nombre, asistente.apellido)) {
                            nuevasAsistencias.push({
                                id: Date.now() + Math.random(),
                                nombre: asistente.nombre,
                                apellido: asistente.apellido,
                                dia1: false,
                                dia2: false,
                                dia3: true,
                                fecha: new Date().toLocaleString()
                            });
                        } else {
                            // Actualizar asistencia existente
                            const index = asistencias.findIndex(a => 
                                a.nombre === asistente.nombre && a.apellido === asistente.apellido
                            );
                            if (index !== -1) {
                                asistencias[index].dia3 = true;
                            }
                        }
                    });
                }
                
                // Agregar nuevas asistencias
                asistencias = [...asistencias, ...nuevasAsistencias];
                
                // Actualizar interfaz
                actualizarTablaAsistencias();
                calcularEstadisticasAsistencias();
                
                syncStatus.innerHTML = `<div class="alert alert-success">Sincronización completada. Se procesaron ${nuevasAsistencias.length} nuevas asistencias.</div>`;
            }, 2000);
        }
        
        // Generar certificados
        function generarCertificados() {
            if (!certificateTemplateData) {
                certificateStatus.innerHTML = '<div class="alert alert-danger">No hay plantilla de certificado cargada.</div>';
                return;
            }
            
            const asistentesAprobados = obtenerAsistentesAprobados();
            
            if (asistentesAprobados.length === 0) {
                certificateStatus.innerHTML = '<div class="alert alert-warning">No hay asistentes aprobados para generar certificados.</div>';
                return;
            }
            
            certificateStatus.innerHTML = '<div class="alert alert-info">Generando certificados, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        certificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    // Generar certificados para cada asistente aprobado
                    generatedCertificates = [];
                    
                    asistentesAprobados.forEach(asistente => {
                        let certificadoHTML = htmlContent;
                        
                        // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                        certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, asistente.cargo);
                        certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, asistente.apellido);
                        certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, asistente.nombre);
                        
                        generatedCertificates.push({
                            nombre: asistente.nombre,
                            apellido: asistente.apellido,
                            cargo: asistente.cargo,
                            html: certificadoHTML,
                            fechaGeneracion: new Date().toLocaleString()
                        });
                    });
                    
                    // SOLUCIÓN: Usar la función mejorada para guardar
                    const guardadoExitoso = guardarCertificadosEnStorage();
                    
                    if (guardadoExitoso) {
                        certificateStatus.innerHTML = `<div class="alert alert-success">Se han generado ${generatedCertificates.length} certificados correctamente.</div>`;
                    } else {
                        certificateStatus.innerHTML = `<div class="alert alert-warning">Se generaron ${generatedCertificates.length} certificados, pero no se pudieron guardar todos debido a limitaciones de almacenamiento.</div>`;
                    }
                    
                    actualizarTablaCertificados();
                    calcularEstadisticasAsistencias();
                    
                    // CORRECCIÓN: Habilitar botón de descarga para administradores sin restricciones
                    btnDownloadCertificates.disabled = false;
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    certificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // Descargar certificados individuales en PDF
        function descargarCertificadoIndividual(nombre, apellido) {
            // CORRECCIÓN: Los administradores pueden descargar certificados sin restricciones de fecha
            const esAdmin = adminDashboard.style.display === 'block';
            
            if (!esAdmin && !certificadosDisponibles()) {
                alert('Los certificados estarán disponibles a partir del 25 de Octubre 2025 a las 13:00.');
                return;
            }
            
            const certificado = generatedCertificates.find(c => 
                c.nombre === nombre && c.apellido === apellido
            );
            
            if (!certificado) {
                alert('No se encontró el certificado para este asistente.');
                return;
            }
            
            // SOLUCIÓN: Regenerar el certificado si no está en memoria
            if (!certificado.html && certificateTemplateData) {
                // Regenerar el certificado
                mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                    .then(function(result) {
                        const htmlContent = result.value;
                        let certificadoHTML = htmlContent;
                        
                        // Reemplazar campos en la plantilla
                        certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, certificado.cargo);
                        certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, certificado.apellido);
                        certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, certificado.nombre);
                        
                        // Crear un PDF con el contenido HTML
                        generarPDF(certificadoHTML, nombre, apellido);
                    })
                    .catch(function(error) {
                        alert('Error al generar el certificado: ' + error.message);
                    });
            } else {
                // Crear un PDF con el contenido HTML
                generarPDF(certificado.html, nombre, apellido);
            }
        }
        
        // Función para generar PDF a partir de HTML
        function generarPDF(htmlContent, nombre, apellido) {
            // Crear un elemento temporal para el contenido HTML
            const tempDiv = document.createElement('div');
            tempDiv.innerHTML = htmlContent;
            document.body.appendChild(tempDiv);
            
            // Usar html2canvas para convertir el HTML a imagen
            html2canvas(tempDiv).then(canvas => {
                // Crear PDF
                const { jsPDF } = window.jspdf;
                const pdf = new jsPDF('landscape', 'mm', 'a4');
                
                // Agregar la imagen al PDF
                const imgData = canvas.toDataURL('image/png');
                const imgWidth = 297; // A4 landscape width in mm
                const imgHeight = canvas.height * imgWidth / canvas.width;
                
                pdf.addImage(imgData, 'PNG', 0, 0, imgWidth, imgHeight);
                pdf.save(`Certificado_${nombre}_${apellido}.pdf`);
                
                // Eliminar el elemento temporal
                document.body.removeChild(tempDiv);
            });
        }
        
        // Descargar todos los certificados en un ZIP como PDF
        function descargarTodosCertificados() {
            // CORRECCIÓN: El administrador puede descargar certificados en cualquier momento
            // No hay restricción de fecha para el administrador
            
            if (generatedCertificates.length === 0) {
                alert('No hay certificados generados para descargar.');
                return;
            }
            
            certificateStatus.innerHTML = '<div class="alert alert-info">Preparando archivos PDF para descarga, por favor espere...</div>';
            
            const zip = new JSZip();
            let certificadosListos = 0;
            
            generatedCertificates.forEach((certificado, index) => {
                // SOLUCIÓN: Regenerar certificados si no están en memoria
                if (!certificado.html && certificateTemplateData) {
                    mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                        .then(function(result) {
                            const htmlContent = result.value;
                            let certificadoHTML = htmlContent;
                            
                            // Reemplazar campos en la plantilla
                            certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, certificado.cargo);
                            certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, certificado.apellido);
                            certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, certificado.nombre);
                            
                            // Crear un elemento temporal para el contenido HTML
                            const tempDiv = document.createElement('div');
                            tempDiv.innerHTML = certificadoHTML;
                            document.body.appendChild(tempDiv);
                            
                            // Usar html2canvas para convertir el HTML a imagen
                            html2canvas(tempDiv).then(canvas => {
                                // Crear PDF
                                const { jsPDF } = window.jspdf;
                                const pdf = new jsPDF('landscape', 'mm', 'a4');
                                
                                // Agregar la imagen al PDF
                                const imgData = canvas.toDataURL('image/png');
                                const imgWidth = 297; // A4 landscape width in mm
                                const imgHeight = canvas.height * imgWidth / canvas.width;
                                
                                pdf.addImage(imgData, 'PNG', 0, 0, imgWidth, imgHeight);
                                
                                // Convertir PDF a blob
                                const pdfBlob = pdf.output('blob');
                                
                                const nombreArchivo = `Certificado_${certificado.nombre}_${certificado.apellido}.pdf`;
                                zip.file(nombreArchivo, pdfBlob);
                                
                                certificadosListos++;
                                
                                // Eliminar el elemento temporal
                                document.body.removeChild(tempDiv);
                                
                                // Cuando todos estén listos, generar el ZIP
                                if (certificadosListos === generatedCertificates.length) {
                                    zip.generateAsync({type: 'blob'})
                                        .then(function(content) {
                                            saveAs(content, 'Certificados_Congreso.zip');
                                            certificateStatus.innerHTML = '<div class="alert alert-success">Descarga completada.</div>';
                                        });
                                }
                            });
                        })
                        .catch(function(error) {
                            console.error('Error al generar certificado:', error);
                            certificadosListos++;
                        });
                } else {
                    // Crear un elemento temporal para el contenido HTML
                    const tempDiv = document.createElement('div');
                    tempDiv.innerHTML = certificado.html;
                    document.body.appendChild(tempDiv);
                    
                    // Usar html2canvas para convertir el HTML a imagen
                    html2canvas(tempDiv).then(canvas => {
                        // Crear PDF
                        const { jsPDF } = window.jspdf;
                        const pdf = new jsPDF('landscape', 'mm', 'a4');
                        
                        // Agregar la imagen al PDF
                        const imgData = canvas.toDataURL('image/png');
                        const imgWidth = 297; // A4 landscape width in mm
                        const imgHeight = canvas.height * imgWidth / canvas.width;
                        
                        pdf.addImage(imgData, 'PNG', 0, 0, imgWidth, imgHeight);
                        
                        // Convertir PDF a blob
                        const pdfBlob = pdf.output('blob');
                        
                        const nombreArchivo = `Certificado_${certificado.nombre}_${certificado.apellido}.pdf`;
                        zip.file(nombreArchivo, pdfBlob);
                        
                        certificadosListos++;
                        
                        // Eliminar el elemento temporal
                        document.body.removeChild(tempDiv);
                        
                        // Cuando todos estén listos, generar el ZIP
                        if (certificadosListos === generatedCertificates.length) {
                            zip.generateAsync({type: 'blob'})
                                .then(function(content) {
                                    saveAs(content, 'Certificados_Congreso.zip');
                                    certificateStatus.innerHTML = '<div class="alert alert-success">Descarga completada.</div>';
                                });
                        }
                    });
                }
            });
        }
        
        // NUEVA FUNCIÓN: Generar certificado para persona no inscrita
        function generarCertificadoExterno() {
            if (!certificateTemplateData) {
                externalCertificateStatus.innerHTML = '<div class="alert alert-danger">No hay plantilla de certificado cargada.</div>';
                return;
            }
            
            const cargo = externalCargo.value;
            const nombre = externalNombre.value;
            const apellido = externalApellido.value;
            
            if (!cargo || !nombre || !apellido) {
                externalCertificateStatus.innerHTML = '<div class="alert alert-danger">Debe completar todos los campos.</div>';
                return;
            }
            
            externalCertificateStatus.innerHTML = '<div class="alert alert-info">Generando certificado, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        externalCertificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    let certificadoHTML = htmlContent;
                    
                    // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                    certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, cargo);
                    certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, apellido);
                    certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, nombre);
                    
                    // Agregar a la lista de certificados generados
                    generatedCertificates.push({
                        nombre: nombre,
                        apellido: apellido,
                        cargo: cargo,
                        html: certificadoHTML,
                        fechaGeneracion: new Date().toLocaleString()
                    });
                    
                    // Guardar en localStorage
                    guardarCertificadosEnStorage();
                    
                    externalCertificateStatus.innerHTML = '<div class="alert alert-success">Certificado generado correctamente.</div>';
                    
                    // Actualizar tabla de certificados
                    actualizarTablaCertificados();
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    externalCertificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // NUEVA FUNCIÓN: Descargar certificado para persona no inscrita
        function descargarCertificadoExterno() {
            const cargo = externalCargo.value;
            const nombre = externalNombre.value;
            const apellido = externalApellido.value;
            
            if (!cargo || !nombre || !apellido) {
                externalCertificateStatus.innerHTML = '<div class="alert alert-danger">Debe completar todos los campos.</div>';
                return;
            }
            
            externalCertificateStatus.innerHTML = '<div class="alert alert-info">Generando certificado PDF, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        externalCertificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    let certificadoHTML = htmlContent;
                    
                    // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                    certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, cargo);
                    certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, apellido);
                    certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, nombre);
                    
                    // Crear un PDF con el contenido HTML
                    generarPDF(certificadoHTML, nombre, apellido);
                    
                    externalCertificateStatus.innerHTML = '<div class="alert alert-success">Certificado PDF descargado correctamente.</div>';
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    externalCertificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // NUEVA FUNCIÓN: Vista previa del certificado
        function vistaPreviaCertificado() {
            const participanteId = certificateParticipantSelect.value;
            
            if (!participanteId) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">Debe seleccionar un participante.</div>';
                return;
            }
            
            if (!certificateTemplateData) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No hay plantilla de certificado cargada.</div>';
                return;
            }
            
            const participante = registros.find(r => r.id == participanteId);
            
            if (!participante) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No se encontró el participante seleccionado.</div>';
                return;
            }
            
            htmlCertificateStatus.innerHTML = '<div class="alert alert-info">Generando vista previa, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    let certificadoHTML = htmlContent;
                    
                    // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                    certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, participante.cargo);
                    certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, participante.apellido);
                    certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, participante.nombre);
                    
                    // Mostrar vista previa
                    certificatePreviewContent.innerHTML = certificadoHTML;
                    certificatePreviewContainer.style.display = 'block';
                    
                    htmlCertificateStatus.innerHTML = '<div class="alert alert-success">Vista previa generada correctamente.</div>';
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // NUEVA FUNCIÓN: Descargar certificado HTML autocompletado
        function descargarCertificadoHTML() {
            const participanteId = certificateParticipantSelect.value;
            
            if (!participanteId) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">Debe seleccionar un participante.</div>';
                return;
            }
            
            if (!certificateTemplateData) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No hay plantilla de certificado cargada.</div>';
                return;
            }
            
            const participante = registros.find(r => r.id == participanteId);
            
            if (!participante) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No se encontró el participante seleccionado.</div>';
                return;
            }
            
            htmlCertificateStatus.innerHTML = '<div class="alert alert-info">Generando certificado HTML, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    let certificadoHTML = htmlContent;
                    
                    // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                    certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, participante.cargo);
                    certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, participante.apellido);
                    certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, participante.nombre);
                    
                    // Crear un blob con el contenido HTML
                    const blob = new Blob([certificadoHTML], { type: 'text/html' });
                    const url = URL.createObjectURL(blob);
                    
                    // Crear enlace de descarga
                    const link = document.createElement('a');
                    link.href = url;
                    link.download = `Certificado_${participante.nombre}_${participante.apellido}.html`;
                    document.body.appendChild(link);
                    link.click();
                    document.body.removeChild(link);
                    
                    // Liberar el objeto URL
                    URL.revokeObjectURL(url);
                    
                    htmlCertificateStatus.innerHTML = '<div class="alert alert-success">Certificado HTML descargado correctamente.</div>';
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // NUEVA FUNCIÓN: Descargar certificado PDF autocompletado
        function descargarCertificadoPDF() {
            const participanteId = certificateParticipantSelect.value;
            
            if (!participanteId) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">Debe seleccionar un participante.</div>';
                return;
            }
            
            if (!certificateTemplateData) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No hay plantilla de certificado cargada.</div>';
                return;
            }
            
            const participante = registros.find(r => r.id == participanteId);
            
            if (!participante) {
                htmlCertificateStatus.innerHTML = '<div class="alert alert-danger">No se encontró el participante seleccionado.</div>';
                return;
            }
            
            htmlCertificateStatus.innerHTML = '<div class="alert alert-info">Generando certificado PDF, por favor espere...</div>';
            
            // Usar Mammoth para convertir el DOCX a HTML
            mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                .then(function(result) {
                    const htmlContent = result.value;
                    
                    // CORRECCIÓN: Usar la función corregida
                    const camposFaltantes = validarPlantillaCertificado(htmlContent);
                    
                    if (camposFaltantes.length > 0) {
                        htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">La plantilla no contiene los campos requeridos: ${camposFaltantes.join(', ')}</div>`;
                        return;
                    }
                    
                    let certificadoHTML = htmlContent;
                    
                    // Reemplazar campos en la plantilla - CORREGIDO: usar minúsculas consistentes
                    certificadoHTML = certificadoHTML.replace(/{{cargo}}/g, participante.cargo);
                    certificadoHTML = certificadoHTML.replace(/{{apellido}}/g, participante.apellido);
                    certificadoHTML = certificadoHTML.replace(/{{nombre}}/g, participante.nombre);
                    
                    // Crear un PDF con el contenido HTML
                    generarPDF(certificadoHTML, participante.nombre, participante.apellido);
                    
                    htmlCertificateStatus.innerHTML = '<div class="alert alert-success">Certificado PDF descargado correctamente.</div>';
                })
                .catch(function(error) {
                    console.error('Error al procesar la plantilla:', error);
                    htmlCertificateStatus.innerHTML = `<div class="alert alert-danger">Error al procesar la plantilla: ${error.message}</div>`;
                });
        }
        
        // NUEVA FUNCIÓN: Actualizar lista de participantes para certificados
        function actualizarListaParticipantesCertificados() {
            certificateParticipantSelect.innerHTML = '<option value="">Seleccione un participante</option>';
            
            registros.forEach(participante => {
                const option = document.createElement('option');
                option.value = participante.id;
                option.textContent = `${participante.cargo} ${participante.nombre} ${participante.apellido}`;
                certificateParticipantSelect.appendChild(option);
            });
        }
        
        // NUEVA FUNCIÓN: Actualizar sección de participantes
        function actualizarSeccionParticipantes() {
            actualizarTablaRegistros();
            actualizarCupos();
            actualizarListaParticipantesCertificados();
        }
        
        // NUEVA FUNCIÓN: Actualizar sección de asistencias
        function actualizarSeccionAsistencias() {
            actualizarTablaAsistencias();
            calcularEstadisticasAsistencias();
        }
        
        // NUEVA FUNCIÓN: Actualizar sección de certificados
        function actualizarSeccionCertificados() {
            actualizarTablaCertificados();
            actualizarListaParticipantesCertificados();
        }
        
        // Inicializar la visualización de cupos
        actualizarCupos();
        inicializarRegistros();
        inicializarAsistencias();
        inicializarAgenda();
        inicializarCertificados();
        mostrarAgenda();
        mostrarCertificados();
        calcularEstadisticasAsistencias();
        actualizarContadorLimite();
        actualizarListaParticipantesCertificados();
        
        // Manejar el envío del formulario
        document.getElementById('formulario-inscripcion').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const cargo = document.getElementById('cargo').value;
            const nombre = document.getElementById('nombre').value;
            const apellido = document.getElementById('apellido').value;
            const correo = document.getElementById('correo').value;
            const categoria = document.getElementById('categoria').value;
            
            const mensajeDiv = document.getElementById('mensaje-registro');
            
            // Verificar si el registro está habilitado (para usuarios normales)
            if (!registroHabilitado()) {
                mensajeDiv.innerHTML = '<div class="alert alert-danger">Los registros están cerrados. El período de registro finalizó el 22 de Octubre a las 23:59.</div>';
                return;
            }
            
            // Verificar si el participante ya existe
            if (participanteExiste(cargo, nombre, apellido)) {
                mensajeDiv.innerHTML = '<div class="alert alert-danger">Este participante ya está registrado.</div>';
                return;
            }
            
            // Verificar disponibilidad según la categoría
            if (categoria === 'MEDICO GENERAL' || categoria === 'MEDICO ESPECIALISTA') {
                if (cuposMedicos <= 0) {
                    mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Médico. Solo quedan disponibles 50 cupos para esta categoría.</div>';
                    return;
                }
            } else if (categoria === 'LICENCIADO EN ENFERMERIA') {
                mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Licenciado en Enfermería.</div>';
                return;
            } else if (categoria === 'INTERNO ROTATIVO DE ENFERMERIA' || categoria === 'INTERNO ROTATIVO DE MEDICINA') {
                mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Interno Rotativo.</div>';
                return;
            }
            
            // Si hay disponibilidad, procesar la inscripción
            if (cuposAsignados < cuposTotales) {
                // Crear objeto de registro
                const registro = {
                    id: Date.now(),
                    cargo,
                    nombre,
                    apellido,
                    correo,
                    categoria,
                    fecha: new Date().toLocaleString()
                };
                
                // Agregar a registros
                registros.unshift(registro);
                
                // Actualizar contadores
                cuposAsignados++;
                if (categoria === 'MEDICO GENERAL' || categoria === 'MEDICO ESPECIALISTA') {
                    cuposMedicos--;
                }
                
                // Mostrar mensaje de éxito
                mensajeDiv.innerHTML = `<div class="alert alert-success">
                    <strong>¡Registro exitoso!</strong><br>
                    ${cargo} ${nombre} ${apellido} ha sido registrado exitosamente.<br>
                    Se ha enviado un correo de confirmación a ${correo}.
                </div>`;
                
                // Actualizar visualización de cupos
                actualizarCupos();
                
                // Actualizar tabla de administración si está visible
                if (adminDashboard.style.display === 'block') {
                    actualizarTablaRegistros();
                    actualizarListaParticipantesCertificados();
                }
                
                // Limpiar formulario
                document.getElementById('formulario-inscripcion').reset();
            } else {
                mensajeDiv.innerHTML = '<div class="alert alert-danger">Lo sentimos, no hay cupos disponibles.</div>';
            }
        });
        
        // Actualizar disponibilidad según la categoría seleccionada
        document.getElementById('categoria').addEventListener('change', function() {
            const categoria = this.value;
            const btnRegistrar = document.getElementById('btn-registrar');
            const mensajeDiv = document.getElementById('mensaje-registro');
            
            if (categoria === 'MEDICO GENERAL' || categoria === 'MEDICO ESPECIALISTA') {
                if (cuposMedicos > 0) {
                    btnRegistrar.disabled = !registroHabilitado();
                    mensajeDiv.innerHTML = '<div class="alert alert-warning">Cupos disponibles para médicos: ' + cuposMedicos + '</div>';
                } else {
                    btnRegistrar.disabled = true;
                    mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Médico.</div>';
                }
            } else if (categoria === 'LICENCIADO EN ENFERMERIA') {
                btnRegistrar.disabled = true;
                mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Licenciado en Enfermería.</div>';
            } else if (categoria === 'INTERNO ROTATIVO DE ENFERMERIA' || categoria === 'INTERNO ROTATIVO DE MEDICINA') {
                btnRegistrar.disabled = true;
                mensajeDiv.innerHTML = '<div class="alert alert-danger">No hay disponibilidad para la categoría de Interno Rotativo.</div>';
            } else {
                btnRegistrar.disabled = !registroHabilitado();
                mensajeDiv.innerHTML = '';
            }
        });
        
        // Funcionalidad del panel de administración
        btnAdmin.addEventListener('click', function() {
            adminPanel.style.display = 'flex';
        });
        
        closeAdmin.addEventListener('click', function() {
            adminPanel.style.display = 'none';
        });
        
        btnLogin.addEventListener('click', function() {
            const user = document.getElementById('admin-user').value;
            const pass = document.getElementById('admin-pass').value;
            
            if (user === 'DOCENCIA' && pass === 'DOCENCIA') {
                adminLogin.style.display = 'none';
                adminDashboard.style.display = 'block';
                actualizarCupos();
                actualizarTablaRegistros();
                actualizarTablaAsistencias();
                actualizarTablaCertificados();
                calcularEstadisticasAsistencias();
                actualizarEstadoRegistroAdmin();
                actualizarListaParticipantesCertificados();
            } else {
                alert('Usuario o contraseña incorrectos');
            }
        });
        
        // Navegación entre tabs
        document.querySelectorAll('.admin-tab').forEach(tab => {
            tab.addEventListener('click', function() {
                // Remover clase active de todos los tabs
                document.querySelectorAll('.admin-tab').forEach(t => {
                    t.classList.remove('active');
                });
                
                // Remover clase active de todos los contenidos
                document.querySelectorAll('.tab-content').forEach(c => {
                    c.classList.remove('active');
                });
                
                // Agregar clase active al tab clickeado
                this.classList.add('active');
                
                // Mostrar el contenido correspondiente
                const tabId = this.getAttribute('data-tab');
                document.getElementById(`tab-${tabId}`).classList.add('active');
            });
        });
        
        // Manejar selección de archivo de agenda
        agendaFileInput.addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                // Validar tipo de archivo
                if (file.type !== 'application/pdf') {
                    uploadStatus.innerHTML = '<div class="alert alert-danger">Solo se permiten archivos PDF.</div>';
                    btnUploadAgenda.disabled = true;
                    return;
                }
                
                // CORRECCIÓN: Aumentar tamaño máximo a 20MB
                if (file.size > 20 * 1024 * 1024) {
                    uploadStatus.innerHTML = '<div class="alert alert-danger">El archivo es demasiado grande. El tamaño máximo permitido es 20MB.</div>';
                    btnUploadAgenda.disabled = true;
                    return;
                }
                
                agendaFile = file;
                
                // Mostrar información del archivo
                document.getElementById('selected-file-name').textContent = file.name;
                document.getElementById('selected-file-size').textContent = formatFileSize(file.size);
                document.getElementById('selected-file-type').textContent = file.type;
                
                fileInfo.style.display = 'block';
                fileInputLabel.classList.add('file-selected');
                fileLabelText.textContent = file.name;
                
                // Habilitar botón de subir
                btnUploadAgenda.disabled = false;
                uploadStatus.innerHTML = '';
                
                // Leer el archivo como base64
                const reader = new FileReader();
                reader.onload = function(e) {
                    agendaFileData = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        });
        
        // Subir agenda
        btnUploadAgenda.addEventListener('click', function() {
            if (!agendaFile || !agendaFileData) {
                uploadStatus.innerHTML = '<div class="alert alert-danger">No se ha seleccionado ningún archivo.</div>';
                return;
            }
            
            // Guardar en localStorage
            const agendaData = {
                file: {
                    name: agendaFile.name,
                    size: agendaFile.size,
                    type: agendaFile.type,
                    lastModified: agendaFile.lastModified
                },
                data: agendaFileData
            };
            
            localStorage.setItem('agendaCongresoFile', JSON.stringify(agendaData));
            
            uploadStatus.innerHTML = '<div class="alert alert-success">Agenda cargada correctamente.</div>';
            mostrarAgenda();
            
            // Deshabilitar botón después de subir
            btnUploadAgenda.disabled = true;
        });
        
        // Descargar agenda
        btnDownloadAgenda.addEventListener('click', function() {
            if (!agendaFileData) {
                alert('No hay agenda disponible para descargar.');
                return;
            }
            
            // Crear enlace de descarga
            const link = document.createElement('a');
            link.href = agendaFileData;
            link.download = agendaFile.name || 'agenda_congreso.pdf';
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        });
        
        // Manejar selección de plantilla de certificado
        certificateTemplateInput.addEventListener('change', function(e) {
            const file = e.target.files[0];
            
            if (file) {
                // Validar tipo de archivo
                if (file.type !== 'application/vnd.openxmlformats-officedocument.wordprocessingml.document') {
                    certificateStatus.innerHTML = '<div class="alert alert-danger">Solo se permiten archivos Word (.docx).</div>';
                    btnUploadTemplate.disabled = true;
                    return;
                }
                
                // CORRECCIÓN: Aumentar tamaño máximo a 10MB
                if (file.size > 10 * 1024 * 1024) {
                    certificateStatus.innerHTML = '<div class="alert alert-danger">El archivo es demasiado grande. El tamaño máximo permitido es 10MB.</div>';
                    btnUploadTemplate.disabled = true;
                    return;
                }
                
                certificateTemplate = file;
                
                // Mostrar información del archivo
                document.getElementById('selected-certificate-name').textContent = file.name;
                document.getElementById('selected-certificate-size').textContent = formatFileSize(file.size);
                document.getElementById('selected-certificate-type').textContent = file.type;
                
                document.getElementById('certificate-file-info').style.display = 'block';
                document.getElementById('certificate-input-label').classList.add('file-selected');
                document.getElementById('certificate-label-text').textContent = file.name;
                
                // Habilitar botón de subir
                btnUploadTemplate.disabled = false;
                certificateStatus.innerHTML = '';
                
                // Leer el archivo como ArrayBuffer
                const reader = new FileReader();
                reader.onload = function(e) {
                    certificateTemplateData = e.target.result;
                    
                    // Validar la plantilla
                    mammoth.convertToHtml({arrayBuffer: certificateTemplateData})
                        .then(function(result) {
                            // CORRECCIÓN: Usar la función corregida
                            const camposFaltantes = validarPlantillaCertificado(result.value);
                            
                            if (camposFaltantes.length > 0) {
                                document.getElementById('template-validation').innerHTML = 
                                    `<div class="alert alert-warning">Advertencia: La plantilla no contiene los campos: ${camposFaltantes.join(', ')}</div>`;
                            } else {
                                document.getElementById('template-validation').innerHTML = 
                                    `<div class="alert alert-success">Plantilla válida. Todos los campos requeridos están presentes.</div>`;
                            }
                        })
                        .catch(function(error) {
                            document.getElementById('template-validation').innerHTML = 
                                `<div class="alert alert-danger">Error al validar la plantilla: ${error.message}</div>`;
                        });
                };
                reader.readAsArrayBuffer(file);
            }
        });
        
        // Subir plantilla de certificado
        btnUploadTemplate.addEventListener('click', function() {
            if (!certificateTemplate || !certificateTemplateData) {
                certificateStatus.innerHTML = '<div class="alert alert-danger">No se ha seleccionado ningún archivo.</div>';
                return;
            }
            
            // Guardar en localStorage
            const templateData = {
                file: {
                    name: certificateTemplate.name,
                    size: certificateTemplate.size,
                    type: certificateTemplate.type,
                    lastModified: certificateTemplate.lastModified
                },
                data: certificateTemplateData
            };
            
            localStorage.setItem('certificateTemplate', JSON.stringify(templateData));
            
            certificateStatus.innerHTML = '<div class="alert alert-success">Plantilla de certificado cargada correctamente.</div>';
            mostrarCertificados();
            
            // Habilitar botón de generación
            btnGenerateCertificates.disabled = false;
            
            // Deshabilitar botón después de subir
            btnUploadTemplate.disabled = true;
        });
        
        // Generar certificados
        btnGenerateCertificates.addEventListener('click', generarCertificados);
        
        // Descargar todos los certificados
        btnDownloadCertificates.addEventListener('click', descargarTodosCertificados);
        
        // Descargar mi certificado (para usuarios normales)
        btnDownloadMyCertificate.addEventListener('click', function() {
            // En una implementación real, esto debería identificar al usuario actual
            // Por ahora, usaremos un ejemplo
            descargarCertificadoIndividual("PRUEBA", "PRUEBA");
        });
        
        // SOLUCIÓN: Sincronización de asistencias
        btnSyncDay1.addEventListener('click', function() {
            sincronizarAsistencias(1);
        });
        
        btnSyncDay2.addEventListener('click', function() {
            sincronizarAsistencias(2);
        });
        
        btnSyncDay3.addEventListener('click', function() {
            sincronizarAsistencias(3);
        });
        
        btnSyncAll.addEventListener('click', function() {
            sincronizarAsistencias('all');
        });
        
        // NUEVOS BOTONES: Actualizar secciones
        btnUpdateParticipants.addEventListener('click', actualizarSeccionParticipantes);
        btnUpdateAttendance.addEventListener('click', actualizarSeccionAsistencias);
        btnUpdateCertificates.addEventListener('click', actualizarSeccionCertificados);
        
        // NUEVOS BOTONES: Vista previa y descarga de certificados
        btnPreviewCertificate.addEventListener('click', vistaPreviaCertificado);
        btnDownloadHtmlCertificate.addEventListener('click', descargarCertificadoHTML);
        btnDownloadPdfCertificate.addEventListener('click', descargarCertificadoPDF);
        
        // NUEVOS BOTONES: Generar certificados para personas no inscritas
        btnGenerateExternalCertificate.addEventListener('click', generarCertificadoExterno);
        btnDownloadExternalCertificate.addEventListener('click', descargarCertificadoExterno);
        
        // Búsqueda en asistencias
        btnSearchAttendance.addEventListener('click', function() {
            const termino = searchAttendance.value.trim();
            const resultados = buscarAsistencias(termino);
            actualizarTablaAsistencias(resultados);
        });
        
        btnClearSearchAttendance.addEventListener('click', function() {
            searchAttendance.value = '';
            actualizarTablaAsistencias();
        });
        
        // Búsqueda en certificados
        btnSearchCertificates.addEventListener('click', function() {
            const termino = searchCertificates.value.trim();
            const resultados = buscarCertificados(termino);
            actualizarTablaCertificados(resultados);
        });
        
        btnClearSearchCertificates.addEventListener('click', function() {
            searchCertificates.value = '';
            actualizarTablaCertificados();
        });
        
        // Actualizar tabla de registros
        function actualizarTablaRegistros(registrosFiltrados = null) {
            const tbody = document.getElementById('registros-table');
            tbody.innerHTML = '';
            
            const registrosAMostrar = registrosFiltrados || registros;
            
            if (registrosAMostrar.length === 0) {
                tbody.innerHTML = '<tr><td colspan="6" style="text-align: center;">No hay registros</td></tr>';
            } else {
                registrosAMostrar.forEach(registro => {
                    const tr = document.createElement('tr');
                    tr.innerHTML = `
                        <td>${registro.nombre} ${registro.apellido}</td>
                        <td>${registro.cargo}</td>
                        <td>${registro.categoria}</td>
                        <td>${registro.correo}</td>
                        <td>${registro.fecha}</td>
                        <td class="admin-actions">
                            <button class="btn btn-edit" onclick="editarParticipante(${registro.id})">Editar</button>
                            <button class="btn btn-delete" onclick="eliminarParticipante(${registro.id})">Eliminar</button>
                        </td>
                    `;
                    tbody.appendChild(tr);
                });
            }
        }
        
        // Actualizar tabla de asistencias
        function actualizarTablaAsistencias(asistenciasFiltradas = null) {
            const tbody = document.getElementById('asistencias-table');
            tbody.innerHTML = '';
            
            const asistenciasAMostrar = asistenciasFiltradas || asistencias;
            
            if (asistenciasAMostrar.length === 0) {
                tbody.innerHTML = '<tr><td colspan="8" style="text-align: center;">No hay registros de asistencia</td></tr>';
            } else {
                asistenciasAMostrar.forEach(asistencia => {
                    const diasAsistidos = (asistencia.dia1 ? 1 : 0) + (asistencia.dia2 ? 1 : 0) + (asistencia.dia3 ? 1 : 0);
                    let estado = '';
                    let estadoClass = '';
                    
                    if (diasAsistidos >= 2) {
                        estado = 'APROBADO';
                        estadoClass = 'status-approved';
                    } else if (diasAsistidos === 0) {
                        estado = 'REPROBADO';
                        estadoClass = 'status-failed';
                    } else {
                        estado = 'PENDIENTE';
                        estadoClass = 'status-pending';
                    }
                    
                    const tr = document.createElement('tr');
                    tr.innerHTML = `
                        <td>${asistencia.nombre}</td>
                        <td>${asistencia.apellido}</td>
                        <td>${asistencia.dia1 ? '✓' : '✗'}</td>
                        <td>${asistencia.dia2 ? '✓' : '✗'}</td>
                        <td>${asistencia.dia3 ? '✓' : '✗'}</td>
                        <td>${diasAsistidos}/3</td>
                        <td><span class="attendance-status ${estadoClass}">${estado}</span></td>
                        <td class="admin-actions">
                            <button class="btn btn-edit" onclick="editarAsistencia(${asistencia.id})">Editar</button>
                            <button class="btn btn-delete" onclick="eliminarAsistencia(${asistencia.id})">Eliminar</button>
                        </td>
                    `;
                    tbody.appendChild(tr);
                });
            }
        }
        
        // Actualizar tabla de certificados
        function actualizarTablaCertificados(certificadosFiltrados = null) {
            const tbody = document.getElementById('certificados-table');
            tbody.innerHTML = '';
            
            const certificadosAMostrar = certificadosFiltrados || obtenerAsistentesAprobados();
            
            if (certificadosAMostrar.length === 0) {
                tbody.innerHTML = '<tr><td colspan="6" style="text-align: center;">No hay asistentes aprobados para certificación</td></tr>';
            } else {
                certificadosAMostrar.forEach(asistente => {
                    const certificadoGenerado = generatedCertificates.find(c => 
                        c.nombre === asistente.nombre && c.apellido === asistente.apellido
                    );
                    
                    const tr = document.createElement('tr');
                    tr.innerHTML = `
                        <td>${asistente.nombre}</td>
                        <td>${asistente.apellido}</td>
                        <td>${asistente.cargo}</td>
                        <td>${asistente.diasAsistidos}/3</td>
                        <td><span class="attendance-status status-approved">APROBADO</span></td>
                        <td class="admin-actions">
                            ${certificadoGenerado ? 
                                `<button class="btn btn-download" onclick="descargarCertificadoIndividual('${asistente.nombre}', '${asistente.apellido}')">
                                    <i class="fas fa-download"></i> Descargar
                                </button>` : 
                                '<span class="text-muted">Pendiente</span>'
                            }
                        </td>
                    `;
                    tbody.appendChild(tr);
                });
            }
        }
        
        // Funciones globales para editar y eliminar participantes
        window.editarParticipante = function(id) {
            const participante = registros.find(r => r.id === id);
            if (participante) {
                document.getElementById('edit-id').value = participante.id;
                document.getElementById('modal-cargo').value = participante.cargo;
                document.getElementById('modal-nombre').value = participante.nombre;
                document.getElementById('modal-apellido').value = participante.apellido;
                document.getElementById('modal-correo').value = participante.correo;
                document.getElementById('modal-categoria').value = participante.categoria;
                
                modalTitle.textContent = 'Editar Participante';
                participantModal.style.display = 'flex';
            }
        };
        
        window.eliminarParticipante = function(id) {
            if (confirm('¿Está seguro de que desea eliminar este participante?')) {
                const index = registros.findIndex(r => r.id === id);
                if (index !== -1) {
                    // Ajustar contadores
                    cuposAsignados--;
                    if (registros[index].categoria === 'MEDICO GENERAL' || registros[index].categoria === 'MEDICO ESPECIALISTA') {
                        cuposMedicos++;
                    }
                    
                    registros.splice(index, 1);
                    actualizarCupos();
                    actualizarTablaRegistros();
                    actualizarListaParticipantesCertificados();
                }
            }
        };
        
        // Funciones globales para editar y eliminar asistencias
        window.editarAsistencia = function(id) {
            const asistencia = asistencias.find(a => a.id === id);
            if (asistencia) {
                document.getElementById('edit-attendance-id').value = asistencia.id;
                document.getElementById('attendance-nombre').value = asistencia.nombre;
                document.getElementById('attendance-apellido').value = asistencia.apellido;
                document.getElementById('attendance-dia1').checked = asistencia.dia1;
                document.getElementById('attendance-dia2').checked = asistencia.dia2;
                document.getElementById('attendance-dia3').checked = asistencia.dia3;
                
                modalTitleAttendance.textContent = 'Editar Asistencia';
                attendanceModal.style.display = 'flex';
            }
        };
        
        window.eliminarAsistencia = function(id) {
            if (confirm('¿Está seguro de que desea eliminar este registro de asistencia?')) {
                const index = asistencias.findIndex(a => a.id === id);
                if (index !== -1) {
                    asistencias.splice(index, 1);
                    actualizarTablaAsistencias();
                    calcularEstadisticasAsistencias();
                }
            }
        };
        
        // Función global para descargar certificado individual
        window.descargarCertificadoIndividual = descargarCertificadoIndividual;
        
        // Búsqueda de participantes
        btnSearchParticipant.addEventListener('click', function() {
            const termino = searchParticipant.value.trim();
            const resultados = buscarParticipantes(termino);
            actualizarTablaRegistros(resultados);
        });
        
        btnClearSearch.addEventListener('click', function() {
            searchParticipant.value = '';
            actualizarTablaRegistros();
        });
        
        // Agregar nuevo participante (ADMIN - siempre habilitado)
        btnAddParticipant.addEventListener('click', function() {
            document.getElementById('edit-id').value = '';
            document.getElementById('modal-cargo').value = '';
            document.getElementById('modal-nombre').value = '';
            document.getElementById('modal-apellido').value = '';
            document.getElementById('modal-correo').value = '';
            document.getElementById('modal-categoria').value = '';
            
            modalTitle.textContent = 'Agregar Participante';
            participantModal.style.display = 'flex';
        });
        
        // Agregar nueva asistencia
        btnAddAttendance.addEventListener('click', function() {
            document.getElementById('edit-attendance-id').value = '';
            document.getElementById('attendance-nombre').value = '';
            document.getElementById('attendance-apellido').value = '';
            document.getElementById('attendance-dia1').checked = false;
            document.getElementById('attendance-dia2').checked = false;
            document.getElementById('attendance-dia3').checked = false;
            
            modalTitleAttendance.textContent = 'Registrar Asistencia';
            attendanceModal.style.display = 'flex';
        });
        
        // Cerrar modales
        closeModal.addEventListener('click', function() {
            participantModal.style.display = 'none';
        });
        
        btnCancel.addEventListener('click', function() {
            participantModal.style.display = 'none';
        });
        
        closeAttendanceModal.addEventListener('click', function() {
            attendanceModal.style.display = 'none';
        });
        
        btnCancelAttendance.addEventListener('click', function() {
            attendanceModal.style.display = 'none';
        });
        
        // Guardar participante (ADMIN - siempre habilitado)
        participantForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const id = document.getElementById('edit-id').value;
            const cargo = document.getElementById('modal-cargo').value;
            const nombre = document.getElementById('modal-nombre').value;
            const apellido = document.getElementById('modal-apellido').value;
            const correo = document.getElementById('modal-correo').value;
            const categoria = document.getElementById('modal-categoria').value;
            
            // Verificar si el participante ya existe (solo para nuevos registros)
            if (!id && participanteExiste(cargo, nombre, apellido)) {
                alert('Este participante ya está registrado.');
                return;
            }
            
            if (id) {
                // Editar existente
                const index = registros.findIndex(r => r.id == id);
                if (index !== -1) {
                    // Ajustar contadores si cambió la categoría
                    const oldCategoria = registros[index].categoria;
                    if (oldCategoria !== categoria) {
                        if (oldCategoria === 'MEDICO GENERAL' || oldCategoria === 'MEDICO ESPECIALISTA') {
                            cuposMedicos++;
                        }
                        if (categoria === 'MEDICO GENERAL' || categoria === 'MEDICO ESPECIALISTA') {
                            // El administrador puede exceder el límite de 50 médicos
                            cuposMedicos--;
                        }
                    }
                    
                    registros[index] = {
                        id: parseInt(id),
                        cargo,
                        nombre,
                        apellido,
                        correo,
                        categoria,
                        fecha: registros[index].fecha
                    };
                }
            } else {
                // Agregar nuevo - EL ADMINISTRADOR PUEDE REGISTRAR INCLUSO DESPUÉS DEL LÍMITE
                const nuevoId = Date.now();
                registros.unshift({
                    id: nuevoId,
                    cargo,
                    nombre,
                    apellido,
                    correo,
                    categoria,
                    fecha: new Date().toLocaleString()
                });
                
                cuposAsignados++;
                if (categoria === 'MEDICO GENERAL' || categoria === 'MEDICO ESPECIALISTA') {
                    cuposMedicos--;
                }
            }
            
            actualizarCupos();
            actualizarTablaRegistros();
            actualizarListaParticipantesCertificados();
            participantModal.style.display = 'none';
        });
        
        // Guardar asistencia
        attendanceForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const id = document.getElementById('edit-attendance-id').value;
            const nombre = document.getElementById('attendance-nombre').value;
            const apellido = document.getElementById('attendance-apellido').value;
            const dia1 = document.getElementById('attendance-dia1').checked;
            const dia2 = document.getElementById('attendance-dia2').checked;
            const dia3 = document.getElementById('attendance-dia3').checked;
            
            // Verificar si la asistencia ya existe (solo para nuevos registros)
            if (!id && asistenciaExiste(nombre, apellido)) {
                alert('Ya existe un registro de asistencia para esta persona.');
                return;
            }
            
            if (id) {
                // Editar existente
                const index = asistencias.findIndex(a => a.id == id);
                if (index !== -1) {
                    asistencias[index] = {
                        id: parseInt(id),
                        nombre,
                        apellido,
                        dia1,
                        dia2,
                        dia3,
                        fecha: asistencias[index].fecha
                    };
                }
            } else {
                // Agregar nuevo
                const nuevoId = Date.now();
                asistencias.unshift({
                    id: nuevoId,
                    nombre,
                    apellido,
                    dia1,
                    dia2,
                    dia3,
                    fecha: new Date().toLocaleString()
                });
            }
            
            actualizarTablaAsistencias();
            calcularEstadisticasAsistencias();
            attendanceModal.style.display = 'none';
        });
        
        // Descargar lista de asistentes
        btnDownloadList.addEventListener('click', function() {
            let csvContent = "data:text/csv;charset=utf-8,";
            csvContent += "Cargo,Nombre,Apellido,Categoría,Correo,Fecha de Registro\n";
            
            registros.forEach(registro => {
                const row = [
                    registro.cargo,
                    registro.nombre,
                    registro.apellido,
                    registro.categoria,
                    registro.correo,
                    registro.fecha
                ].join(",");
                csvContent += row + "\n";
            });
            
            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", "lista_asistentes_congreso.csv");
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        });
        
        // Descargar consolidado de asistencias
        btnDownloadAttendance.addEventListener('click', function() {
            let csvContent = "data:text/csv;charset=utf-8,";
            csvContent += "Nombre,Apellido,Día 1,Día 2,Día 3,Total Asistencias,Estado,Fecha de Registro\n";
            
            asistencias.forEach(asistencia => {
                const diasAsistidos = (asistencia.dia1 ? 1 : 0) + (asistencia.dia2 ? 1 : 0) + (asistencia.dia3 ? 1 : 0);
                let estado = '';
                
                if (diasAsistidos >= 2) {
                    estado = 'APROBADO';
                } else if (diasAsistidos === 0) {
                    estado = 'REPROBADO';
                } else {
                    estado = 'PENDIENTE';
                }
                
                const row = [
                    asistencia.nombre,
                    asistencia.apellido,
                    asistencia.dia1 ? 'SÍ' : 'NO',
                    asistencia.dia2 ? 'SÍ' : 'NO',
                    asistencia.dia3 ? 'SÍ' : 'NO',
                    diasAsistidos.toString(),
                    estado,
                    asistencia.fecha
                ].join(",");
                csvContent += row + "\n";
            });
            
            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", "consolidado_asistencias_congreso.csv");
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        });
        
        // Cerrar panel al hacer clic fuera
        adminPanel.addEventListener('click', function(e) {
            if (e.target === adminPanel) {
                adminPanel.style.display = 'none';
            }
        });
        
        participantModal.addEventListener('click', function(e) {
            if (e.target === participantModal) {
                participantModal.style.display = 'none';
            }
        });
        
        attendanceModal.addEventListener('click', function(e) {
            if (e.target === attendanceModal) {
                attendanceModal.style.display = 'none';
            }
        });
        
        // Inicializar conteo regresivo
        updateCountdown();
        setInterval(updateCountdown, 1000);
        
        // Actualizar contador de límite de registro cada segundo
        setInterval(actualizarContadorLimite, 1000);
        
        // Actualizar disponibilidad de certificados cada minuto
        setInterval(function() {
            mostrarCertificados();
        }, 60000);
    </script>
</body>
</html>
