<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El Viaje del Héroe Territorial | Manabí</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --verde-musgo: #2C4A31;
            --azul-umina: #1E5F8A;
            --tierra: #8B6B4A;
            --fuego-azul: #4A90E2;
            --blanco-roto: #FAFAFA;
            --negro-carbon: #1A1A1A;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--blanco-roto);
            color: var(--negro-carbon);
            scroll-behavior: smooth;
        }

        h1, h2, h3, .font-cinzel {
            font-family: 'Cinzel', serif;
        }

        .hero-gradient {
            background: linear-gradient(rgba(26, 26, 26, 0.6), rgba(26, 26, 26, 0.6)), 
                        url('https://images.unsplash.com/photo-1501785888041-af3ef285b470?auto=format&fit=crop&q=80&w=2070');
            background-size: cover;
            background-position: center;
        }

        .station-card:hover .station-overlay {
            opacity: 1;
        }

        .glass-nav {
            background: rgba(44, 74, 49, 0.9);
            backdrop-filter: blur(10px);
        }

        .btn-primary {
            background-color: var(--azul-umina);
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            background-color: #154666;
            transform: translateY(-2px);
        }

        .attribute-icon {
            color: var(--tierra);
        }

        .bg-fuego-azul { background: linear-gradient(135deg, #4A90E2 0%, #00D9FF 100%); }
        .bg-agua { background: linear-gradient(135deg, #1E5F8A 0%, #50C878 100%); }
        
        .fade-in {
            animation: fadeIn 1s ease-in forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Acordeón personalizado */
        .faq-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        .faq-item.active .faq-content {
            max-height: 200px;
        }
        .faq-item.active i {
            transform: rotate(180deg);
        }
    </style>
</head>
<body>

    <!-- Navegación -->
    <nav class="fixed w-full z-50 glass-nav text-white">
        <div class="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-emerald-900 font-bold">VH</div>
                <span class="font-cinzel tracking-widest text-lg hidden md:block">EL VIAJE DEL HÉROE</span>
            </div>
            
            <div class="hidden md:flex space-x-8 text-sm font-medium tracking-wide">
                <a href="#inicio" class="hover:text-emerald-200 transition">INICIO</a>
                <a href="#el-viaje" class="hover:text-emerald-200 transition">EL VIAJE</a>
                <a href="#experiencia" class="hover:text-emerald-200 transition">EXPERIENCIA</a>
                <a href="#recursos" class="hover:text-emerald-200 transition">RECURSOS</a>
                <a href="#inscripcion" class="bg-white text-emerald-900 px-4 py-2 rounded-full font-bold hover:bg-emerald-100 transition">INSCRÍBETE</a>
            </div>

            <button class="md:hidden text-2xl" id="menuBtn">
                <i class="fas fa-bars"></i>
            </button>
        </div>
    </nav>

    <!-- Mobile Menu -->
    <div id="mobileMenu" class="fixed inset-0 bg-emerald-900 z-40 hidden flex-col items-center justify-center space-y-8 text-white text-2xl font-cinzel">
        <button class="absolute top-6 right-6" id="closeBtn"><i class="fas fa-times"></i></button>
        <a href="#inicio" onclick="toggleMenu()">INICIO</a>
        <a href="#el-viaje" onclick="toggleMenu()">EL VIAJE</a>
        <a href="#experiencia" onclick="toggleMenu()">EXPERIENCIA</a>
        <a href="#inscripcion" onclick="toggleMenu()">INSCRIPCIÓN</a>
    </div>

    <!-- Hero Section -->
    <header id="inicio" class="hero-gradient h-screen flex items-center justify-center text-center text-white px-4">
        <div class="max-w-4xl fade-in">
            <h1 class="text-5xl md:text-8xl font-bold mb-6 tracking-tighter">EL TERRITORIO TE LLAMA</h1>
            <p class="text-xl md:text-2xl mb-10 font-light max-w-2xl mx-auto">Un viaje épico de transformación personal y conexión con la memoria sagrada de Manabí.</p>
            <div class="flex flex-col md:flex-row justify-center gap-4">
                <a href="#inscripcion" class="btn-primary text-white px-8 py-4 rounded-full text-lg font-bold">COMIENZA TU VIAJE →</a>
                <a href="#el-viaje" class="border-2 border-white px-8 py-4 rounded-full text-lg font-bold hover:bg-white hover:text-black transition">DESCUBRE MÁS</a>
            </div>
        </div>
    </header>

    <!-- Sección 2: Introducción -->
    <section class="py-24 px-4 bg-white">
        <div class="max-w-5xl mx-auto text-center">
            <h2 class="text-3xl md:text-5xl mb-8 leading-tight">No es solo un recorrido.<br>Es un regreso a tu origen.</h2>
            <p class="text-lg md:text-xl text-gray-600 mb-16 leading-relaxed">
                El Viaje del Héroe Territorial es una experiencia inmersiva que transforma la geografía en memoria y al caminante en guardián. A través de 4 estaciones sagradas en el corazón de Manabí, descubrirás que el territorio no es un mapa: es un llamado.
            </p>
            
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
                <div class="p-6 border-r border-gray-100 last:border-0">
                    <div class="text-4xl mb-2">🏔️</div>
                    <div class="text-3xl font-bold font-cinzel">4</div>
                    <div class="text-gray-500 text-sm">Estaciones</div>
                </div>
                <div class="p-6 border-r border-gray-100 last:border-0">
                    <div class="text-4xl mb-2">👥</div>
                    <div class="text-3xl font-bold font-cinzel">+500</div>
                    <div class="text-gray-500 text-sm">Guardianes</div>
                </div>
                <div class="p-6 border-r border-gray-100 last:border-0">
                    <div class="text-4xl mb-2">🌿</div>
                    <div class="text-3xl font-bold font-cinzel">1</div>
                    <div class="text-gray-500 text-sm">Territorio Vivo</div>
                </div>
                <div class="p-6">
                    <div class="text-4xl mb-2">⏱️</div>
                    <div class="text-3xl font-bold font-cinzel">4</div>
                    <div class="text-gray-500 text-sm">Días de Viaje</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección 3: Las 4 Estaciones -->
    <section id="el-viaje" class="py-24 px-4 bg-gray-50">
        <div class="max-w-7xl mx-auto">
            <h2 class="text-center text-4xl mb-16 font-cinzel tracking-widest">CUATRO ESTACIONES. UNA TRANSFORMACIÓN.</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Dadal -->
                <div class="relative overflow-hidden rounded-2xl h-96 group shadow-lg">
                    <img src="https://images.unsplash.com/photo-1544413660-299165566b1d?auto=format&fit=crop&q=80&w=800" alt="Dadal" class="absolute inset-0 w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
                    <div class="absolute bottom-0 p-8 text-white">
                        <span class="text-2xl mb-2 block">👂</span>
                        <h3 class="text-2xl font-bold mb-2 font-cinzel">DADAL: EL UMBRAL</h3>
                        <p class="text-sm opacity-90 mb-4">Donde aprendes a escuchar el latido de la tierra.</p>
                        <button onclick="showDetails('dadal')" class="text-xs font-bold tracking-widest border-b border-white pb-1">SABER MÁS →</button>
                    </div>
                </div>

                <!-- Choconchá -->
                <div class="relative overflow-hidden rounded-2xl h-96 group shadow-lg">
                    <img src="https://images.unsplash.com/photo-1500382017468-9049fed747ef?auto=format&fit=crop&q=80&w=800" alt="Choconchá" class="absolute inset-0 w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
                    <div class="absolute bottom-0 p-8 text-white">
                        <span class="text-2xl mb-2 block">👁️</span>
                        <h3 class="text-2xl font-bold mb-2 font-cinzel">CHOCONCHÁ: EL ESPEJO</h3>
                        <p class="text-sm opacity-90 mb-4">Donde el agua refleja quién eres realmente.</p>
                        <button onclick="showDetails('choconcha')" class="text-xs font-bold tracking-widest border-b border-white pb-1">SABER MÁS →</button>
                    </div>
                </div>

                <!-- Agua Dulce -->
                <div class="relative overflow-hidden rounded-2xl h-96 group shadow-lg">
                    <img src="https://images.unsplash.com/photo-1518709268805-4e9042af9f23?auto=format&fit=crop&q=80&w=800" alt="Agua Dulce" class="absolute inset-0 w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
                    <div class="absolute bottom-0 p-8 text-white">
                        <span class="text-2xl mb-2 block">📖</span>
                        <h3 class="text-2xl font-bold mb-2 font-cinzel">AGUA DULCE: LA MATRIZ</h3>
                        <p class="text-sm opacity-90 mb-4">Donde la memoria teje tu lugar en la historia.</p>
                        <button onclick="showDetails('aguadulce')" class="text-xs font-bold tracking-widest border-b border-white pb-1">SABER MÁS →</button>
                    </div>
                </div>

                <!-- Fuego Azul -->
                <div class="relative overflow-hidden rounded-2xl h-96 group shadow-lg">
                    <img src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&q=80&w=800" alt="Fuego Azul" class="absolute inset-0 w-full h-full object-cover transition duration-500 group-hover:scale-110">
                    <div class="absolute inset-0 bg-gradient-to-t from-blue-900/80 to-transparent"></div>
                    <div class="absolute bottom-0 p-8 text-white">
                        <span class="text-2xl mb-2 block">💙</span>
                        <h3 class="text-2xl font-bold mb-2 font-cinzel">EL RETORNO: EL GUARDIÁN</h3>
                        <p class="text-sm opacity-90 mb-4">Donde despierta el guardián que llevas dentro.</p>
                        <button onclick="showDetails('fuegoazul')" class="text-xs font-bold tracking-widest border-b border-white pb-1">SABER MÁS →</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal de Detalles (Simplificado) -->
    <div id="detailModal" class="fixed inset-0 bg-black/90 z-[100] hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full max-h-[90vh] overflow-y-auto relative p-8 md:p-12">
            <button onclick="hideDetails()" class="absolute top-6 right-6 text-2xl text-gray-400 hover:text-black transition"><i class="fas fa-times"></i></button>
            <div id="modalContent"></div>
        </div>
    </div>

    <!-- Sección 4: Atributos -->
    <section class="py-24 px-4 text-white" style="background-color: var(--verde-musgo);">
        <div class="max-w-7xl mx-auto">
            <h2 class="text-center text-4xl mb-16 font-cinzel tracking-widest">CUATRO ATRIBUTOS DEL GUARDIÁN</h2>
            <div class="grid grid-cols-1 md:grid-cols-4 gap-12 text-center">
                <div class="space-y-4">
                    <div class="text-6xl text-emerald-400">👂</div>
                    <h3 class="text-2xl font-bold font-cinzel">EL OÍDO</h3>
                    <p class="text-gray-300">Escuchar el territorio en sus silencios y latidos.</p>
                </div>
                <div class="space-y-4">
                    <div class="text-6xl text-blue-400">👁️</div>
                    <h3 class="text-2xl font-bold font-cinzel">LA MIRADA</h3>
                    <p class="text-gray-300">Ver más allá de la superficie y lo evidente.</p>
                </div>
                <div class="space-y-4">
                    <div class="text-6xl text-amber-400">📖</div>
                    <h3 class="text-2xl font-bold font-cinzel">LA PALABRA</h3>
                    <p class="text-gray-300">Tejer la memoria colectiva en cada relato.</p>
                </div>
                <div class="space-y-4">
                    <div class="text-6xl text-red-400">💙</div>
                    <h3 class="text-2xl font-bold font-cinzel">EL CORAZÓN</h3>
                    <p class="text-gray-300">Comprometerse con la vida y la custodia.</p>
                </div>
            </div>
            <div class="text-center mt-16">
                <button class="bg-amber-500 hover:bg-amber-600 text-white font-bold px-10 py-4 rounded-full transition transform hover:scale-105">DESCUBRE TU ATRIBUTO →</button>
            </div>
        </div>
    </section>

    <!-- Sección 5: Testimonios -->
    <section class="py-24 px-4 bg-white">
        <div class="max-w-7xl mx-auto">
            <h2 class="text-center text-4xl mb-16 font-cinzel">HISTORIAS DE GUARDIANES</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-50 p-8 rounded-3xl border border-gray-100 italic relative">
                    <i class="fas fa-quote-left absolute top-6 left-6 text-gray-200 text-4xl"></i>
                    <p class="relative z-10 text-gray-700 mb-6">"Pensé que iba a subir una montaña. Terminé encontrándome a mí mismo. El territorio me enseñó que ser guardián no es un título, es un compromiso diario."</p>
                    <div class="flex items-center space-x-4 not-italic">
                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                        <div>
                            <p class="font-bold text-sm">María Elena</p>
                            <p class="text-xs text-gray-500">24 años, Jipijapa</p>
                        </div>
                    </div>
                </div>
                <div class="bg-gray-50 p-8 rounded-3xl border border-gray-100 italic relative">
                    <i class="fas fa-quote-left absolute top-6 left-6 text-gray-200 text-4xl"></i>
                    <p class="relative z-10 text-gray-700 mb-6">"Choconchá me mostró una verdad que llevaba años evitando. Salí del agua diferente. Ahora veo el territorio con otros ojos."</p>
                    <div class="flex items-center space-x-4 not-italic">
                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                        <div>
                            <p class="font-bold text-sm">Carlos</p>
                            <p class="text-xs text-gray-500">19 años, Portoviejo</p>
                        </div>
                    </div>
                </div>
                <div class="bg-gray-50 p-8 rounded-3xl border border-gray-100 italic relative">
                    <i class="fas fa-quote-left absolute top-6 left-6 text-gray-200 text-4xl"></i>
                    <p class="relative z-10 text-gray-700 mb-6">"La bitácora se convirtió en mi compañera. Cada trazo, cada palabra, me ató más a mi historia. Soy eslabón de una cadena que no se romperá."</p>
                    <div class="flex items-center space-x-4 not-italic">
                        <div class="w-12 h-12 bg-gray-300 rounded-full"></div>
                        <div>
                            <p class="font-bold text-sm">Ana Lucía</p>
                            <p class="text-xs text-gray-500">22 años, Montecristi</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección 6: Itinerario -->
    <section id="experiencia" class="py-24 px-4 bg-gray-50">
        <div class="max-w-5xl mx-auto">
            <h2 class="text-center text-4xl mb-16 font-cinzel">ITINERARIO DEL VIAJE</h2>
            <div class="space-y-6">
                <!-- Dia 1 -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border-l-4 border-emerald-700">
                    <div class="flex justify-between items-center mb-4">
                        <span class="bg-emerald-100 text-emerald-800 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-widest">Día 1</span>
                        <span class="text-gray-400"><i class="fas fa-mountain mr-2"></i>Dificultad: ⭐⭐⭐☆☆</span>
                    </div>
                    <h3 class="text-2xl font-bold font-cinzel mb-2">DADAL: ASCENSO A LA PIRÁMIDE</h3>
                    <p class="text-gray-600 mb-4">Ascenso por la columna vertebral del ancestro hasta la Ceiba Monumental.</p>
                    <ul class="text-sm space-y-2 text-gray-500">
                        <li><i class="far fa-clock mr-2"></i>06:00 - Encuentro en punto de partida</li>
                        <li><i class="fas fa-leaf mr-2"></i>09:00 - Ceremonia en Cueva de Piedra Verde</li>
                        <li><i class="fas fa-burn mr-2"></i>10:30 - Ceremonia del Carbón en la cima</li>
                    </ul>
                </div>

                <!-- Dia 2 -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border-l-4 border-blue-700">
                    <div class="flex justify-between items-center mb-4">
                        <span class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-widest">Día 2</span>
                        <span class="text-gray-400"><i class="fas fa-water mr-2"></i>Dificultad: ⭐⭐☆☆☆</span>
                    </div>
                    <h3 class="text-2xl font-bold font-cinzel mb-2">CHOCONCHÁ: EL ESPEJO DE AGUA</h3>
                    <p class="text-gray-600 mb-4">Descenso al corazón de la tierra para limpiar la mirada en los pozos sagrados.</p>
                    <ul class="text-sm space-y-2 text-gray-500">
                        <li><i class="far fa-clock mr-2"></i>08:00 - Caminata hacia los pozos</li>
                        <li><i class="fas fa-tint mr-2"></i>10:00 - Ejercicio del espejo e inmersión</li>
                        <li><i class="fas fa-pen mr-2"></i>13:30 - Registro en bitácora</li>
                    </ul>
                </div>

                <!-- Dia 3 -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border-l-4 border-amber-700">
                    <div class="flex justify-between items-center mb-4">
                        <span class="bg-amber-100 text-amber-800 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-widest">Día 3</span>
                        <span class="text-gray-400"><i class="fas fa-campground mr-2"></i>Dificultad: ⭐⭐☆☆☆</span>
                    </div>
                    <h3 class="text-2xl font-bold font-cinzel mb-2">AGUA DULCE: EL VIENTRE DE PIEDRA</h3>
                    <p class="text-gray-600 mb-4">Círculo de palabra y memoria alrededor del fuego con María Meseia.</p>
                    <ul class="text-sm space-y-2 text-gray-500">
                        <li><i class="far fa-clock mr-2"></i>09:30 - Ingreso a la Cueva de Agua Dulce</li>
                        <li><i class="fas fa-fire mr-2"></i>10:00 - Historia de las 16 Cacicas</li>
                        <li><i class="fas fa-link mr-2"></i>15:00 - Tejido del Hilo de María Meseia</li>
                    </ul>
                </div>

                <!-- Dia 4 -->
                <div class="bg-white p-6 rounded-2xl shadow-sm border-l-4 border-blue-400">
                    <div class="flex justify-between items-center mb-4">
                        <span class="bg-blue-50 text-blue-600 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-widest">Día 4</span>
                        <span class="text-gray-400"><i class="fas fa-star mr-2"></i>Dificultad: ⭐⭐⭐☆☆</span>
                    </div>
                    <h3 class="text-2xl font-bold font-cinzel mb-2">FUEGO AZUL: EL PACTO FINAL</h3>
                    <p class="text-gray-600 mb-4">Ceremonia de cierre en la hora azul donde brota la llama del guardián.</p>
                    <ul class="text-sm space-y-2 text-gray-500">
                        <li><i class="far fa-clock mr-2"></i>17:00 - Ceremonia del Fuego Azul</li>
                        <li><i class="fas fa-file-contract mr-2"></i>18:30 - Lectura del Acta de Custodia</li>
                        <li><i class="fas fa-certificate mr-2"></i>20:30 - Entrega de certificados</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Sección 7: Inscripción -->
    <section id="inscripcion" class="py-24 px-4 bg-white">
        <div class="max-w-4xl mx-auto">
            <div class="bg-gray-900 rounded-[3rem] p-8 md:p-16 text-white text-center mb-16 relative overflow-hidden">
                <div class="absolute inset-0 bg-agua opacity-20"></div>
                <div class="relative z-10">
                    <h2 class="text-3xl md:text-5xl font-cinzel mb-6">¿LISTO PARA ESCUCHAR EL LLAMADO?</h2>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 text-left mb-10 max-w-lg mx-auto">
                        <div>
                            <p class="text-xs uppercase tracking-widest text-emerald-400 font-bold mb-1">Próxima Salida</p>
                            <p class="text-xl">15 - 18 Mayo 2026</p>
                        </div>
                        <div>
                            <p class="text-xs uppercase tracking-widest text-emerald-400 font-bold mb-1">Ubicación</p>
                            <p class="text-xl">Jipijapa, Manabí</p>
                        </div>
                        <div>
                            <p class="text-xs uppercase tracking-widest text-emerald-400 font-bold mb-1">Cupos</p>
                            <p class="text-xl">20 Guardianes</p>
                        </div>
                        <div>
                            <p class="text-xs uppercase tracking-widest text-emerald-400 font-bold mb-1">Inversión</p>
                            <p class="text-xl">$XXX.00 USD</p>
                        </div>
                    </div>
                    <div id="countdown" class="flex justify-center space-x-4 mb-8">
                        <!-- Contador dinámico -->
                        <div class="bg-white/10 p-4 rounded-xl min-w-[70px]">
                            <span class="text-2xl font-bold block">24</span>
                            <span class="text-[10px] uppercase">Días</span>
                        </div>
                        <div class="bg-white/10 p-4 rounded-xl min-w-[70px]">
                            <span class="text-2xl font-bold block">12</span>
                            <span class="text-[10px] uppercase">Horas</span>
                        </div>
                        <div class="bg-white/10 p-4 rounded-xl min-w-[70px]">
                            <span class="text-2xl font-bold block">45</span>
                            <span class="text-[10px] uppercase">Min</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="bg-gray-50 p-8 md:p-12 rounded-3xl border border-gray-100 shadow-xl">
                <h3 class="text-3xl font-cinzel mb-8 text-center">FORMULARIO DE REGISTRO</h3>
                <form id="registrationForm" class="space-y-6">
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="space-y-2">
                            <label class="text-sm font-bold text-gray-700">Nombre Completo</label>
                            <input type="text" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-emerald-500 focus:border-transparent outline-none transition" placeholder="Tu nombre...">
                        </div>
                        <div class="space-y-2">
                            <label class="text-sm font-bold text-gray-700">Email</label>
                            <input type="email" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-emerald-500 focus:border-transparent outline-none transition" placeholder="tu@email.com">
                        </div>
                        <div class="space-y-2">
                            <label class="text-sm font-bold text-gray-700">WhatsApp</label>
                            <input type="tel" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-emerald-500 focus:border-transparent outline-none transition" placeholder="+593...">
                        </div>
                        <div class="space-y-2">
                            <label class="text-sm font-bold text-gray-700">Ciudad de Origen</label>
                            <input type="text" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-emerald-500 focus:border-transparent outline-none transition" placeholder="Ej. Portoviejo">
                        </div>
                    </div>
                    
                    <div class="space-y-2">
                        <label class="text-sm font-bold text-gray-700">¿Por qué quieres realizar este viaje?</label>
                        <textarea rows="4" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:ring-2 focus:ring-emerald-500 outline-none transition" placeholder="Comparte tu motivación con nosotros..."></textarea>
                    </div>

                    <div class="flex items-start space-x-3 p-4 bg-white rounded-xl border border-gray-100">
                        <input type="checkbox" required class="mt-1 w-5 h-5 text-emerald-600 rounded">
                        <span class="text-sm text-gray-500">Declaro que mi condición física es adecuada para la actividad (senderismo moderado de 4-6km diarios) y acepto los términos y condiciones.</span>
                    </div>

                    <button type="submit" class="w-full btn-primary text-white font-bold py-4 rounded-xl text-lg shadow-lg">COMPLETAR INSCRIPCIÓN</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Sección 8: FAQ -->
    <section class="py-24 px-4 bg-gray-50">
        <div class="max-w-3xl mx-auto">
            <h2 class="text-center text-3xl font-cinzel mb-12">PREGUNTAS FRECUENTES</h2>
            <div class="space-y-4" id="faqContainer">
                <!-- FAQ Item 1 -->
                <div class="faq-item bg-white rounded-2xl border border-gray-100 cursor-pointer" onclick="toggleFaq(this)">
                    <div class="p-6 flex justify-between items-center">
                        <h4 class="font-bold">¿Necesito experiencia previa en caminatas?</h4>
                        <i class="fas fa-chevron-down text-gray-400 transition"></i>
                    </div>
                    <div class="faq-content px-6 pb-6 text-gray-600 text-sm">
                        No. El viaje está diseñado para todos los niveles. Solo necesitas disposición, curiosidad y respeto profundo por el territorio sagrado.
                    </div>
                </div>
                <!-- FAQ Item 2 -->
                <div class="faq-item bg-white rounded-2xl border border-gray-100 cursor-pointer" onclick="toggleFaq(this)">
                    <div class="p-6 flex justify-between items-center">
                        <h4 class="font-bold">¿Qué incluye la inscripción?</h4>
                        <i class="fas fa-chevron-down text-gray-400 transition"></i>
                    </div>
                    <div class="faq-content px-6 pb-6 text-gray-600 text-sm">
                        Incluye guía especializado, alimentación ancestral, materiales de trabajo (bitácora física, tarjetas de atributos), audio-guías de preparación, seguro de viaje y la ceremonia del Fuego Azul.
                    </div>
                </div>
                <!-- FAQ Item 3 -->
                <div class="faq-item bg-white rounded-2xl border border-gray-100 cursor-pointer" onclick="toggleFaq(this)">
                    <div class="p-6 flex justify-between items-center">
                        <h4 class="font-bold">¿Cuál es la dificultad física?</h4>
                        <i class="fas fa-chevron-down text-gray-400 transition"></i>
                    </div>
                    <div class="faq-content px-6 pb-6 text-gray-600 text-sm">
                        La dificultad es moderada. Se caminan entre 4 y 6 km diarios con desniveles. Recomendamos tener una condición física básica y calzado adecuado para montaña.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-zinc-950 text-white pt-24 pb-12 px-4">
        <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-12 border-b border-white/10 pb-16">
            <div class="space-y-6">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-white rounded-full flex items-center justify-center text-black font-bold">VH</div>
                    <span class="font-cinzel tracking-widest text-lg">EL VIAJE DEL HÉROE</span>
                </div>
                <p class="text-gray-400 text-sm leading-relaxed">Transformando la geografía en memoria y al caminante en guardián de la vida en Manabí.</p>
                <div class="flex space-x-4">
                    <a href="#" class="w-10 h-10 bg-white/5 rounded-full flex items-center justify-center hover:bg-emerald-600 transition"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="w-10 h-10 bg-white/5 rounded-full flex items-center justify-center hover:bg-blue-600 transition"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" class="w-10 h-10 bg-white/5 rounded-full flex items-center justify-center hover:bg-red-600 transition"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            
            <div>
                <h4 class="font-cinzel text-lg mb-6">ENLACES RÁPIDOS</h4>
                <ul class="space-y-3 text-gray-400 text-sm">
                    <li><a href="#" class="hover:text-white transition">El Viaje</a></li>
                    <li><a href="#" class="hover:text-white transition">Experiencia</a></li>
                    <li><a href="#" class="hover:text-white transition">Guardianes</a></li>
                    <li><a href="#" class="hover:text-white transition">Recursos</a></li>
                    <li><a href="#" class="hover:text-white transition">Nosotros</a></li>
                </ul>
            </div>

            <div>
                <h4 class="font-cinzel text-lg mb-6">CONTACTO</h4>
                <ul class="space-y-3 text-gray-400 text-sm">
                    <li><i class="fas fa-envelope mr-3 text-emerald-500"></i> hola@viajedelheroe.org</li>
                    <li><i class="fab fa-whatsapp mr-3 text-emerald-500"></i> +593 XX XXX XXXX</li>
                    <li><i class="fas fa-map-marker-alt mr-3 text-emerald-500"></i> Jipijapa, Manabí, Ecuador</li>
                </ul>
            </div>

            <div>
                <h4 class="font-cinzel text-lg mb-6">COMUNIDAD</h4>
                <p class="text-gray-400 text-xs mb-4">Recibe historias del territorio y prioridad en inscripciones.</p>
                <form class="flex">
                    <input type="email" class="bg-white/5 border border-white/10 rounded-l-xl px-4 py-2 w-full outline-none focus:border-emerald-500" placeholder="Email">
                    <button class="bg-emerald-600 px-4 py-2 rounded-r-xl"><i class="fas fa-paper-plane"></i></button>
                </form>
            </div>
        </div>
        
        <div class="max-w-7xl mx-auto pt-12 flex flex-col md:flex-row justify-between items-center text-xs text-gray-500">
            <p>© 2026 El Viaje del Héroe Territorial. Todos los derechos reservados.</p>
            <div class="flex space-x-6 mt-4 md:mt-0">
                <a href="#">Privacidad</a>
                <a href="#">Términos</a>
                <a href="#">Cookies</a>
            </div>
            <p class="mt-4 md:mt-0">Hecho con 💙 en Manabí, Ecuador</p>
        </div>
    </footer>

    <script>
        // Navegación Mobile
        const menuBtn = document.getElementById('menuBtn');
        const closeBtn = document.getElementById('closeBtn');
        const mobileMenu = document.getElementById('mobileMenu');

        menuBtn.onclick = () => mobileMenu.classList.remove('hidden');
        closeBtn.onclick = () => mobileMenu.classList.add('hidden');

        function toggleMenu() {
            mobileMenu.classList.add('hidden');
        }

        // FAQ Toggle
        function toggleFaq(element) {
            const isActive = element.classList.contains('active');
            document.querySelectorAll('.faq-item').forEach(item => {
                item.classList.remove('active');
            });
            if (!isActive) {
                element.classList.add('active');
            }
        }

        // Detalles Estaciones
        const stations = {
            dadal: {
                title: "DADAL: EL UMBRAL",
                icon: "👂",
                location: "Altos de Dadal, Jipijapa",
                text: "Subir Dadal no es escalar una colina. Es ascender por la columna vertebral de un ancestro. En la cúspide, bajo la Ceiba Monumental, recibirás el Carbón de la Ceiba para iniciar tu bitácora.",
                mantra: "Escucho el latido de la tierra antes de hablar."
            },
            choconcha: {
                title: "CHOCONCHÁ: EL ESPEJO",
                icon: "👁️",
                location: "Pozos de Choconchá",
                text: "Los Pozos de Choconchá son cuencos ceremoniales tallados por manos antiguas. El agua es un espejo absoluto que refleja tu intención más profunda.",
                mantra: "Mi mirada es limpia y ve la verdad."
            },
            aguadulce: {
                title: "AGUA DULCE: LA MATRIZ",
                icon: "📖",
                location: "Cueva de Agua Dulce",
                text: "Buscamos refugio en la cueva donde el tiempo circula. Alrededor de la fogata invocamos a María Meseia y tejemos el hilo que nos ata a nuestra historia.",
                mantra: "Mi voz teje el futuro de mi pueblo."
            },
            fuegoazul: {
                title: "EL RETORNO: EL GUARDIÁN",
                icon: "💙",
                location: "Hora Azul, Pozos de Choconchá",
                text: "El viaje termina donde empezó, pero bajo las estrellas. El fuego que nace del agua representa la voluntad que nace de la memoria. Aquí asumes tu pacto de custodia.",
                mantra: "Soy el fuego que no se apaga."
            }
        };

        function showDetails(id) {
            const s = stations[id];
            const content = `
                <div class="text-center">
                    <span class="text-6xl mb-6 block">${s.icon}</span>
                    <h2 class="text-3xl font-cinzel mb-2">${s.title}</h2>
                    <p class="text-emerald-600 font-bold text-sm uppercase tracking-widest mb-6"><i class="fas fa-map-marker-alt mr-2"></i>${s.location}</p>
                    <div class="h-px bg-gray-100 w-24 mx-auto mb-8"></div>
                    <p class="text-gray-600 leading-relaxed mb-8">${s.text}</p>
                    <div class="bg-gray-50 p-6 rounded-2xl italic text-gray-500">
                        "${s.mantra}"
                    </div>
                    <button onclick="hideDetails()" class="mt-10 btn-primary text-white px-8 py-3 rounded-full text-sm font-bold">ENTENDIDO</button>
                </div>
            `;
            document.getElementById('modalContent').innerHTML = content;
            document.getElementById('detailModal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
        }

        function hideDetails() {
            document.getElementById('detailModal').classList.add('hidden');
            document.body.style.overflow = 'auto';
        }

        // Scroll animations simple observer
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('section').forEach(section => {
            observer.observe(section);
        });

        // Form Submission
        document.getElementById('registrationForm').onsubmit = (e) => {
            e.preventDefault();
            alert('¡Gracias por inscribirte! Pronto recibirás un correo con las instrucciones de pago y preparación.');
            e.target.reset();
        }
    </script>
</body>
</html>
