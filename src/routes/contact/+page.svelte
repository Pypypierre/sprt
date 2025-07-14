<section id="contact-info" class="laptop:pt-40 scroll-mt-20 w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center max-w-7xl">
		<h2 class="text-4xl laptop:text-left text-[#F9B333] font-bold mb-6 pt-10">
			Nos coordonnées
		</h2>
		<div class="flex flex-col space-y-6 md:space-y-8 pt-5">
			<div class="flex items-center space-x-4">
				<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#F9B333]" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
				<path stroke-linecap="round" stroke-linejoin="round" d="M12 21c4-4 7-7.58 7-11A7 7 0 0 0 5 10c0 3.42 3 7 7 11z" />
				<circle cx="12" cy="10" r="3" />
				</svg>
				<p class="text-gray-300 text-lg md:text-xl">Paris, Île-de-France</p>
			</div>

			<div class="flex items-center space-x-4">
				<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#F9B333]" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
				<path stroke-linecap="round" stroke-linejoin="round" d="M22 16.92V21a2 2 0 0 1-2.18 2 19.8 19.8 0 0 1-8.63-3.15 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 1 4.18 2 2 0 0 1 3 2h4.09a2 2 0 0 1 2 1.72 12.2 12.2 0 0 0 .57 2.57 2 2 0 0 1-.45 2.11L8 9.91a16 16 0 0 0 6 6l1.51-1.21a2 2 0 0 1 2.11-.45 12.2 12.2 0 0 0 2.57.57A2 2 0 0 1 22 16.92z"/>
				</svg>
				<p class="text-gray-300 text-lg md:text-xl">07.86.27.96.95</p>
			</div>

			<div class="flex items-center space-x-4">
				<svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-[#F9B333]" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
				<path stroke-linecap="round" stroke-linejoin="round" d="M4 4h16v16H4V4z"/>
				<polyline points="22,6 12,13 2,6"/>
				</svg>
				<p class="text-gray-300 text-lg md:text-xl">contact@sprt-society.com</p>
			</div>
		</div>
	</div>
</section>

<section id="contact-form" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto max-w-7xl">
		<h2 class="text-4xl md:text-5xl font-bold mb-6 text-[#F9B333]">Nous contacter</h2>
		<p class="mb-8 text-gray-300 text-lg leading-relaxed">
			Une question, un projet ? Remplissez ce formulaire et nous reviendrons vers vous dans les plus bref délais.
		</p>

		<form class="space-y-6 w-[60%] mx-auto">
			<!-- Nom -->
			<div>
				<label for="name" class="block mb-2 text-sm font-medium text-gray-300">Nom complet</label>
				<input type="text" id="name" name="name" required
					class="w-full px-4 py-3 bg-[#1f1f1f] border border-gray-600 rounded-lg text-white placeholder-gray-500 focus:outline-none focus:border-[#F9B333] transition" />
			</div>

			<!-- Email -->
			<div>
				<label for="email" class="block mb-2 text-sm font-medium text-gray-300">Email</label>
				<input type="email" id="email" name="email" required
				  class="w-full px-4 py-3 bg-[#1f1f1f] border border-gray-600 rounded-lg text-white placeholder-gray-500 focus:outline-none focus:border-[#F9B333] transition" />
			</div>

			<!-- Sujet -->
			<div>
				<label for="subject" class="block mb-2 text-sm font-medium text-gray-300">Sujet</label>
				<input type="text" id="subject" name="subject"
				  class="w-full px-4 py-3 bg-[#1f1f1f] border border-gray-600 rounded-lg text-white placeholder-gray-500 focus:outline-none focus:border-[#F9B333] transition" />
			</div>

			<!-- Message -->
			<div>
				<label for="message" class="block mb-2 text-sm font-medium text-gray-300">Message</label>
				<textarea id="message" name="message" rows="5" required
				  class="w-full px-4 py-3 bg-[#1f1f1f] border border-gray-600 rounded-lg text-white placeholder-gray-500 focus:outline-none focus:border-[#F9B333] transition"></textarea>
			</div>

			<!-- Bouton -->
			<button type="submit"
				class="px-8 py-3 bg-[#F9B333] text-black font-semibold rounded-full hover:bg-yellow-400 transition">
				Envoyer
			</button>
		</form>
	</div>
</section>