<script>
  import { Table, TableHead, TableHeadCell, TableBody, TableBodyRow, TableBodyCell } from "flowbite-svelte";

  let tab = false;
  const tab_message = ["Afficher l'annexe", "Masquer l'annexe"];
  const showTab = () => {
	tab = !tab;
  };
  const items = [
	{
	  name: "Le droit de réclamation",
	  definition: [
		"Vous avez le droit de saisir à tout moment le Délégué à la protection des données SPRT Society si vous avez une interrogation quant au traitement que nous faisons de vos données ou si vous êtes en désaccord avec ledit traitement.",
		"Il est rappelé que, dans la mesure où la réponse qui vous serait faite ne vous donnerait pas satisfaction, vous disposez de la faculté de vous adresser à l’autorité de régulation en matière de traitement des données personnelles (la CNIL).",
		"Vous avez le droit d’obtenir des informations claires, transparentes et compréhensibles sur la manière dont nous utilisons vos données à caractère personnel et sur l’exercice de vos droits."
	  ]
	},
    { name: "Le droit d'accès et de rectification", definition: "" },
    { name: "Le droit à l'effacement (« droit à l’oubli »)", definition: ""},
    { name: "Le droit à la limitation du traitement", definition: "" },
    { name: "Droit d'opposition au traitement", definition: "Vous pouvez vous opposer à toute utilisation de vos données personnelles si vous pensez que vos droits et libertés fondamentaux à la protection de vos données l’emportent sur notre intérêt légitime à utiliser ces données. Si vous nous présentez une objection, il se peut que nous continuions à utiliser lesdites données personnelles si nous pouvons démontrer que nous avons des intérêts légitimes impérieux pour l’utilisation de ces données."},
    { name: "Le droit de définir des directives quant au sort de vos données après votre décès", definition: "Vous pouvez définir des directives relatives à la conservation, à l'effacement et à la communication de vos données personnelles après votre décès. Ces directives sont générales ou particulières. Les directives générales sont enregistrées auprès d’un tiers de confiance. Les directives particulières le sont auprès du Responsable de traitement tel que défini en tête de la présente Politique."},
    { name: "Le droit d’obtenir une copie de vos données personnelles", definition: "Vous pouvez nous demander de vous fournir une copie de vos données personnelles dans un format structuré, couramment utilisé et lisible sur ordinateur, ou vous pouvez nous demander de les transférer directement à un autre Responsable de traitement (par exemple, une autre société). Vous ne pouvez exercer ce droit que lorsque nous utilisons vos données personnelles dans le cadre d’un contrat avec vous, ou lorsque nous vous avons demandé votre consentement pour utiliser vos données personnelles. Ce droit ne s’applique pas aux données personnelles que nous détenons ou traitons en vertu de notre intérêt légitime, ou qui ne sont pas conservées sous forme numérique."}
  ];
</script>

<section id="title" class="w-full py-40 bg-[#232323] text-white">
  <div class="w-[90%] mx-auto text-left max-w-7xl">
	<h2 class="text-4xl text-[#F9B333] font-bold mb-6">
	  Politique sur la protection des données personnelles
	</h2>
	<div class="flex flex-wrap justify-center items-stretch gap-6 text-center pt-10">
	  <div class="h-full flex flex-col justify-between border border-yellow-400 max-w-xs w-full rounded-lg p-6 hover:bg-yellow-400/10 transition">
		<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8 mx-auto mb-4 text-yellow-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
		  <path stroke-linecap="round" stroke-linejoin="round" d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" />
		</svg>
		<h3 class="text-lg font-semibold text-yellow-400 mb-2">Nous ne revendons pas vos données  personnelles</h3>
		<p class="text-sm text-gray-400">Il se peut que nous transférions vos données personnelles à nos prestataires afin de vous fournir des produits et services adaptés. Elles ne seront utilisées qu'aux seules fins convenues et préalablement acceptées, et non à des fins commerciales.</p>
	  </div>

	  <div class="h-full flex flex-col justify-between border border-yellow-400 max-w-xs w-full rounded-lg p-6 hover:bg-yellow-400/10 transition">
		<svg xmlns="http://www.w3.org/2000/svg" class="w-8 h-8 mx-auto mb-4 text-yellow-400" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
		  <path stroke-linecap="round" stroke-linejoin="round" d="M1 12s4-8 11-8 11 8 11 8-4 8-11 8S1 12 1 12z" />
		  <circle cx="12" cy="12" r="3" />
		</svg>
		<h3 class="text-lg font-semibold text-yellow-400 mb-2">Nous utilisons vos données personnelles qu’à des fins d’authentification</h3>
		<p class="text-sm text-gray-400">Vos données ne seront utilisées que pour vérifier votre identité à des fins juridiques.</p>
	  </div>
	</div>
  </div>
</section>

<section id="Summary" class="py-30 md:w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-center max-w-[80%]">
		<h1 class="text-lg mb-4 md:text-4xl text-[#F9B333] font-bold mb-6 pt-10">
			Politique de confidentialité
		</h1>
		<h2 class="text-base md:text-2xl text-white font-bold mb-6 pt-10">
			Dernière mise à jour : 24 septembre 2025
		</h2>
		<h2 class="text-base md:text-2xl text-white text-left font-bold mb-6 pt-10">
			Sommaire:
		</h2>
		<ul class=" md:items-left list-disc list-inside">
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Intro" class="hover:underline">Introduction</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Covered_data" class="hover:underline">Définitions</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Complaints" class="hover:underline">Présentation du cadre dans lequel sont effectués les traitements de données personnelles par SPRT Society</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Use_of_personal_data" class="hover:underline">Nos engagements quant à vos données personnelles</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Data_transfers" class="hover:underline">Vos droits</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Service_providers" class="hover:underline">Révision de la présente politique</a>
				</li>
				<li class="text-left text-xs text-gray-300 md:text-xl leading-relaxed mt-4">
					<a href="#Data_security" class="hover:underline">Annexe 1 : description de vos droits sur les données traitées</a>
				</li>
			</ul>
		</div>
</section>


<section id="Intro" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Introduction
		</h2>
		<div class="flex flex-col md: items-center pt-5">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				SPRT Society accorde une grande importance à la protection de la vie privée et veille à assurer la protection des données personnelles qu’elle est amenée à collecter et à traiter dans le cadre et pour les besoins de son activité.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				De manière générale(1), SPRT Society est soumises aux règles applicables en matière de protection des données personnelles et en particulier, au règlement général européen sur la protection des données personnelles n°2016/679 du 27 avril 2016 (dit « RGPD ») et à la Loi n°78-17 du 6 janvier 1978 relative à l’informatique, aux fichiers et aux libertés (dite « Loi Informatique et Libertés ») ainsi qu’à toutes les règles de droit national et de droit européen édictées depuis lors et venant compléter, préciser ou modifier les dispositions précitées.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				La présente politique (ci-après la Politique), en ce qu’elle encadre la manière dont SPRT Society collecte et/ou utilise les données personnelles de ses clients, prospects, fournisseurs et prestataires ; elle témoigne de l’engagement pris par SPRT Society de mettre en œuvre les mesures techniques et organisationnelles appropriées durant tout le cycle de traitement de vos données à caractère personnel, que ce soit lors de la collecte, de l’usage, de la conservation ou de la suppression de vos données, de manière à garantir une utilisation loyale et responsable de celles-ci.
			</p>
		</div>
	</div>
</section>

<section id="Definitions" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Définitions
		</h2>
		<div class="pt-5 text-justify">
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Délégué à la Protection des Données (ou DPO) : le Délégué à la protection des données ou « DPO » de SPRT Society est garant du respect, par SPRT Society et ses filiales, de la réglementation sur la protection des données à caractère personnel. Il met en œuvre la présente politique de protection des données à caractère personnel et s’assure, notamment, de la documentation des traitements à l’occasion des projets impactant la protection de ces données. Il identifie les risques de non-conformité à la loi Informatique et Libertés et au RGPD et préconise les mesures adéquates à mettre en place. Il a en charge la sensibilisation des acteurs au respect des problématiques de protection des données à caractère personnel. Enfin, il prend part à la définition des contrôles de second niveau et à l’élaboration du plan d’audit pour les aspects qui les concernent. Référent des sujets CNIL, il est également le point d’entrée en cas de contrôle réglementaire portant sur les données personnelles.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Donnée à caractère personnel (ou Donnée personnelle) : correspond à toute information permettant d’identifier directement ou indirectement une personne physique (exemple : nom, adresse mail, numéro de téléphone, adresse postale, etc.).
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					SPRT Society : dans le cadre des présentes, SPRT Society désigne la société SPRT Society, société par actions simplifiée de droit français. Lorsque nous mentionnons « nous », « notre » ou « nos », nous faisons référence à l’ensemble des membres de SPRT Society, ce pris ensemble ou individuellement.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Personne concernée : désigne la personne à laquelle se rapportent les données qui font l’objet du traitement.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Personne liée : désigne une personne ou une entité sur laquelle vous-même ou un tiers nous fournissez des informations et/ou dont nous avons connaissance d’une autre manière en lien avec notre Relation d’affaires. Une Personne liée peut notamment être – (i) l’administrateur, le dirigeant ou l’employé d’une société, (ii) le trustee, le constituant (settlor) ou le protecteur (protector) d’un trust, (iii) le détenteur à titre fiduciaire (nominee) ou l’ayant droit économique d’un compte, (iv) le détenteur d’intérêts substantiels au titre d’un compte, (v) le détenteur du contrôle, (vi) le bénéficiaire d’un paiement précis, ou (vii) tout représentant ou agent (p. ex. la personne au bénéfice d’une procuration ou d’un droit d’information sur un compte). De manière générale, il vous appartient d’aviser toute personne qui vous serait liée du fait que des informations la concernant nous ont été transmises et de lui remettre copie de la présente Politique et/ou, si celle-ci en dispose, de la politique de Protection des Données propre à l’entité concernée.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Responsable du Traitement : la personne physique ou morale qui détermine les moyens et les finalités du Traitement.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Sous-traitant : la personne physique ou morale, l’autorité publique, le service ou un autre organisme qui traite des Données personnelles pour le compte du Responsable du Traitement.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Traitement : toute opération effectuée sur des données personnelles, qu’elle soit automatisée ou non, concernant la collecte, l’enregistrement, l’organisation, la conservation, la modification, le rapprochement, la récupération, la consultation, l’extraction, l’utilisation, la mise à disposition, l'alignement, la combinaison, l’analyse, l’archivage ainsi que le blocage, l'effacement ou la destruction de données personnelles.
				</li>
			</ul>
		</div>
	</div>
</section>

<section id="DataProcessingFramework" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Présentation du cadre dans lequel sont effectués les traitements de données personnelles par SPRT Society
		</h2>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Cadre général de la politique
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Conformément au Règlement Général sur la Protection des Données et à la Loi Informatique et Libertés de 1978 modifiée, nous nous engageons à respecter et à protéger vos données personnelles. Dans ce cadre, nous avons établi la présente Politique laquelle vise à décrire le dispositif en place au sein de SPRT Society en matière de protection des données personnelles et les conditions dans lesquelles lesdits sous-traitants, chacun pour ce qui le concerne, sont amenées, en leur qualité de responsable de traitement, à collecter et traiter des données personnelles dans le cadre et/ou pour les besoins de leurs activités ou à faire sous-traiter le traitement de ces données par des tiers. Au premier rang de ce dispositif figure, conformément à la règlementation en vigueur, le registre des activités de traitement mis en place pour SPRT Society, lequel recense les traitements de données que nous effectuons et nous permet de piloter l’utilisation faite des données personnelles collectées dans chaque filiale.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Cette Politique vise également à préciser :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					D’une part les personnes susceptibles d’être concernées, la nature des données à caractère personnel concernées, les modalités dans lesquelles lesdites données sont collectées, les finalités de traitement de ces dernières et la licéité des traitements concernés ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					D’autre part les modalités selon lesquelles les personnes concernées par lesdits traitements peuvent mettre en œuvre/exercer les droits dont elles disposent au titre desdites données en vertu de la réglementation en vigueur.
				</li>
			</ul>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Les personnes concernées
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Au regard de la nature de l’activité de SPRT Society, sont susceptibles d’être concernés par les traitements que nous sommes amenés à effectuer :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					D’une part les clients de SPRT Society (ou leurs héritiers ou ayants-droits), les représentants, actionnaires ou bénéficiaires effectifs desdits clients, leurs prospects ainsi plus généralement que les personnes qui visitent leurs sites internet ou leur/nous communiquent par le moyen de leur choix des coordonnées aux fins de la fourniture à leur profit ou à celui de tiers de service en lien avec les activités de SPRT Society. Les données peuvent être collectées soit directement auprès de vous/de tiers mandatés par vous pour nous les transmettre, les organismes de lutte contre la fraude, les autorités ou institutions, …
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					<p> D’autre part et par exemple (sans que la présente liste ait vocation à l’exhaustivité) si vous :</p>
					<ul class="list-disc list-inside">
						<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
							Travaillez avec nous à titre de fournisseur, de prestataire de services ou de sous-traitant ;
						</li>
						<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
							Êtes en relation avec notre société dans le cadre d’un partenariat ;
						</li>
						<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
							Nous êtes présenté(e) par des tiers à des fins de marketing légitimes ; ou
						</li>
						<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
							Participez à un concours ou un évènement que nous organisons ou sponsorisons.
						</li>
					</ul>
				</li>
			</ul>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Nature des données concernées
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Conformément à la règlementation en vigueur, nous ne collectons et n’utilisons que les données à caractère personnel dont nous avons besoin, il peut s’agir notamment de données relatives à :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Votre identité : prénom, nom, genre, date et lieu de naissance, nationalité, spécimen de signature, photo… ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Votre apparence (image, voix), notamment lors d’évènements organisés par SPRT Society auxquels vous participeriez mais également dès lors que la réglementation l’exige ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Des données fiscales vous concernant ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Votre situation professionnelle : emploi, entreprise… ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Votre situation économique et financière : RIB, situation fiscale, origine du patrimoine/des fonds… ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Des opérations/ transactions effectuées et comprenant des données relatives aux bénéficiaires ou donneurs d’ordres ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Des données issues d’échanges et interactions (entretiens, appels téléphoniques, courriers, messages électroniques, chat, accès à nos pages sur les réseaux sociaux ou tout autre type de communication) ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Des données nécessaires pour engager des démarches précontractuelles, ou pour conclure et/ou exécuter les contrats ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Le cas échéant et dans le cadre de nos relations commerciales, vos loisirs et centres d’intérêt.
				</li>
			</ul>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Modalités de collecte
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				La collecte de ces données est effectuée le plus souvent directement auprès de vous lorsque vous visitez notre site internet.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Elle peut également intervenir lorsque vous nous contactez par l’intermédiaire de l’un de nos canaux hors ligne (ex. : formulaires de demande, téléphone et e-mail). Dans certaines hypothèses, les données vous concernant peuvent également nous avoir été fournies par des tiers (directement ou sur notre demande). Ainsi, de nombreux clients entendent parler de nous par l’intermédiaire de l’un de nos apporteurs d’affaires ; ceux-ci peuvent de ce fait nous fournir des données personnelles sur le client considéré. D’autres tiers (membres de la famille, administrateurs, signataires autorisés, et autres contacts pertinents, etc.) sont également susceptibles de nous communiquer des données à caractère personnel.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Pour votre parfaite information, il est précisé que nous pouvons traiter vos données personnelles sans que vous en soyez avisé et/ou sans votre consentement, ce lorsque cela est requis ou autorisé par la réglementation ou la loi.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Nous pouvons enfin collecter des données vous concernant via des sites internet accessibles au public et sur lesquels lesdites données figurent.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				En revanche, nous ne collectons, n’utilisons, ni ne transférons d’informations relatives à des clients de plateforme d’investissement. Les plateformes d’investissement sont seuls responsables de traitement de toutes les données à caractère personnel que vous leur communiquez. Si vous êtes client auprès de l’un de l’une de ces plateformes, veuillez-vous reporter à leur Politique de protection des données ou tout document équivalent.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Nous vous rappelons que :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Si vous choisissez de ne pas fournir les informations nécessaires, nous pourrions ne pas être en mesure de mener à bien nos missions et cela pourrait avoir un impact sur le service que nous vous rendons.
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Si vous êtes amenés à nous fournir des données à caractère personnel sur un tiers, vous devez en aviser formellement celui-ci et vous assurer qu’il consent au partage de ses données et qu’il est satisfait des données que vous nous avez transmises.
				</li>
			</ul>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			finalités de traitement des données collectées
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				En tout état de cause et quelles que soient les circonstances entourant la collecte de ces données personnelles, celle-ci s’inscrit en toute hypothèse dans le respect de la réglementation en vigueur, lesdites données étant, le plus souvent, utilisées dans les circonstances et aux fins suivantes :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Au titre de la conclusion à intervenir ou de l’exécution, lorsque celui-ci est d’ores et déjà conclu, d’un contrat qui nous lie (« nécessité contractuelle ») ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Dans le cadre plus largement de la gestion de la relation client ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour les besoins de nos actions de prospection et de gestion commerciale, ainsi que nos opérations promotionnelles ou de fidélisation, en ce comprises la réalisation d’actions marketing et l’envoi de communications ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour l’élaboration de statistiques, y compris commerciales ou autres analyses de recherche et développement : le traitement est alors fondé sur l’intérêt légitime du responsable de traitement dans le respect des droits et intérêts du client/ de l’investisseur ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour améliorer la qualité de nos services ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour répondre à des demandes que vous nous auriez formulées ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					A l’occasion et pour les besoins de votre participation à un évènement, quelle qu’en soit la nature, que nous organiserons/ sponsoriserions ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Lorsque nous devons nous conformer à une obligation légale, réglementaire ou administrative (« conformité à la loi »), par exemple au titre de nos obligations de connaissance client ou pour vérifier votre identité, aider à détecter, prévenir la fraude et lutter contre la criminalité financière ; ces obligations incluent l’ensemble des mesures nécessaires en vue de nous conformer à la Directive sur la lutte contre le blanchiment de capitaux (LCB), qui précise que la lutte contre le blanchiment de capitaux et le financement du terrorisme doit être considérée comme relevant juridiquement du domaine de l'Ordre Public ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour nous permettre de répondre à des obligations de reporting, notamment d’autorités publiques telles que l’administration fiscale ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour nous permettre de conserver les éléments de preuve attendus en cas de contrôle par le régulateur français, tels que ces éléments sont prévus par le Règlement général de l’AMF ou par la doctrine établie par cette dernière ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Pour permettre d’assurer la gestion et le suivi des réclamations et des contentieux éventuels.
				</li>
			</ul>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Licéité des traitements concernés
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Dans les hypothèses où les traitements considérés ne sont pas justifiés par des obligations contractuelles/ réglementaires (telles celles présentées à titre d’exemple supra), ils reposent alors soit sur notre intérêt légitime (après analyse préliminaire et prise en compte des impacts potentiels, tant positifs que négatifs que lesdits traitements pourraient avoir sur vos droits et libertés), soit sur le fondement de votre consentement que nous aurons alors recueilli au préalable.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Dans l’optique de protéger les droits à la vie privée et de permettre à nos clients/ nos prospects de contrôler l’utilisation de leurs données personnelles, vous pouvez nous demander de mettre un terme aux opérations de marketing direct que nous effectuerions à votre endroit et pour lesquelles vous seriez ciblés, et ce à tout moment. A cette fin, toutes nos communications marketing incluent des liens de désabonnement qui vous aideront à gérer vos préférences en matière de marketing.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Le fait de refuser un type de marketing, par exemple par e-mail ou par téléphone, ne signifie pas que vous êtes désinscrit de toutes les communications marketing. Nous vous prions d’en tenir compte lorsque vous gérez vos préférences.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				De manière générale, nous vous recommandons de consulter régulièrement la Politique de protection des données et les paramètres de préférence qui vous sont accessibles sur les sites/ les plateformes/ les réseaux sociaux que vous utilisez, car ils dicteront la façon dont les publicités et autres messages sont affichés et partagés sur ces médias.
			</p>
		</div>
	</div>
</section>

<section id="engagements" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Nos engagements quant à vos données personnelles
		</h2>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Assurer la protection de vos données
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				La sécurité de vos données personnelles est une priorité. De ce fait, nous mettons en œuvre des mesures de sécurité organisationnelles et techniques appropriées et conformes à l’état de l’art/ de l’état des connaissances afin de garantir un niveau de sécurité adapté aux risques et d’éviter que les données à caractère personnel que nous sommes amenés à traiter ne soient accidentellement perdues, utilisées ou consultées de manière non autorisée, ou encore modifiées ou divulguées. Nous limitons l’accès à vos données à caractère personnel aux seuls employés (et le cas échéant à nos prestataires/sous-traitants) dont la fonction justifie un tel accès. Toutes ces personnes sont soumises à une obligation contractuelle de confidentialité. Nous pouvons toutefois dans certaines hypothèses être amenés à/contraints de partager lesdites données avec des tiers (ne serait-ce dans certaines hypothèses que pour permettre que soit délivrée la prestation par vous requise), à savoir :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Administrations publiques et gouvernementales, autorités compétentes, etc… 
					Exemple : l’Autorité des Marchés Financiers;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Organismes de lutte contre la fraude pour effectuer des vérifications d’identité, détecter et prévenir la fraude et lutter contre la criminalité financière;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Sous-traitants et prestataires
					Exemple : assistant professionnel en charge des appels;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10">
					Partenaires
				</li>
			</ul>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Ces différents acteurs sont eux-mêmes tenus à la protection des données (et plus généralement au respect des règles fixées par le Règlement Général sur la Protection des Données) qui leur seraient transmises, ce en application de la loi et/ou de la réglementation et, dans certains cas, à raison de clauses contractuelles adaptées.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Nous disposons de procédures pour traiter toute violation de données personnelles réelle ou suspectée, ce afin de pouvoir mettre en œuvre au plus tôt une réaction adaptée et prévenir des risques qui comprennent la notification à la Commission Nationale de l’Informatique et des Libertés (CNIL), l’autorité locale chargée du contrôle de la protection des données personnelles, si nécessaire. Lorsque les données ont été transférées à des tiers, sont en place les dispositifs garantissant que nous pourrons prendre toute mesure nécessaire en cas de violation de données intervenant dans l’environnement dudit tiers et portant sur les données personnelles considérées.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Il est toutefois rappelé que, compte tenu des caractéristiques intrinsèques de l’Internet, les données éventuellement transmises via les sites Internet dont nous sommes titulaires/ qui nous sont transmises via les réseaux font l’objet de mesures qui ne peuvent prémunir de tous les risques de détournement et/ou de piratage, ce dont SPRT Society ne saurait être tenue pour responsable.
			</p>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Ne pas faire commerce de vos données traitées
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Ainsi que précédemment mentionné, nous pouvons être amenés à transférer vos données personnelles à des tiers, soit parce que nous y sommes réglementairement contraints, soit afin de fournir des produits et services adaptés.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Elles ne seront utilisées qu'aux seules fins convenues/ justifiant de leur traitement par SPRT Society, et non à des fins commerciales. En tout état de cause, nous nous engageons à ne vendre aucune donnée à caractère personnel à des tiers.
			</p>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Ne pas conserver inutilement vos données
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Les données à caractère personnel ne doivent pas être conservées au-delà de la durée nécessaire à la finalité du traitement.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Cette durée tient notamment compte :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					De celle de la relation qui nous lie à vous ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					De la finalité considérée ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Des contraintes légales et réglementaires auxquelles nous sommes astreints ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Ddes règles relatives à la prescription des actions judiciaires dans l’hypothèse de contentieux éventuels.
				</li>
			</ul>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				A titre d’illustration, les conversations par chat afférents aux opérations d’investissement effectuées dans le cadre de notre activité de gestion de portefeuille pour compte de tiers sont conservés pendant une durée maximum de 5 ans à compter de la date d’enregistrement, ce afin de respecter l’obligation légale de conservation fixée par les articles 321-72 à 321-74 du Règlement Général de l’Autorité des Marchés Financiers.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Plus généralement, nous ne conservons les données à caractère personnel que pendant la durée raisonnablement requise (par application du référentiel précité ou par référence à celui-ci pour les traitements non encore identifiés et intégrés dans ce dispositif) pour la réalisation des finalités telles que mentionnées dans la présente Politique. Pour mémoire, nous pouvons être amenés à conserver des données collectées pour répondre à une finalité même après le terme de celle-ci si cette conservation se justifie par une finalité différente, par exemple pour répondre à des besoins juridiques, réglementaires, fiscaux ou comptables. Ce serait par exemple le cas dans l’hypothèse de la survenance avérée/ raisonnablement probable d’un litige au terme d’une relation contractuelle, et ce pour des durées alors conformes aux besoins de la finalité spécifique que constituerait un tel contentieux.
			</p>
		</div>
		<h3 class="text-base md:text-2xl text-white font-bold mb-6 pt-10 text-left">
			Prendre les précautions nécessaires en cas de transfert éventuel de vos données
		</h3>
		<div class="pt-5 text-justify">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				SPRT Society s’engage à ce que vos données à caractère personnel bénéficient d’un niveau de protection adéquat et cohérent partout où elles peuvent être transférées.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
				Lorsque nous transférons vos données à des sous-traitants/prestataires de services qui nous fournissent un service, nous obtenons des engagements contractuels et des assurances de leur part pour protéger vos données personnelles.
			</p>
		</div>
	</div>
</section>

<section id="rights" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Vos droits
		</h2>
		<div class="flex flex-col md: items-left pt-5">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Conformément à la règlementation en vigueur, vous avez la faculté de nous contacter à propos de vos données personnelles afin de :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Vous assurez de ce que nous détenons (ou pas) et utilisons des données vous concernant ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Connaître l’utilisation que nous en faisons ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Connaître leur(s) destinataire(s) ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Savoir si nous les transférons à l’étranger ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Savoir comment nous les protégeons ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Connaître leur(s) durée(s) de conservation ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Savoir comment nous les avons obtenues ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Savoir si nous avons effectué une prise de décision automatisée à l’aide de vos données personnelles ;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Solliciter une copie desdites données.
				</li>
			</ul>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Vous disposez en outre de différents droits sur vos données personnelles, à savoir, par-delà le droit d'accès susmentionné, la faculté d’obtenir dès lors que la réglementation l’autorise, la rectification et/ou l’effacement par SPRT Society de vos données à caractère personnel mais également celle d’exercer les différents droits suivants relatifs au traitement de vos données : droit à la limitation du traitement, droit de vous opposer au traitement et droit à la portabilité de vos données.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Une présentation plus complète de ces droits et des modalités de leur exercice figure en annexe à la présente « Politique ».
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Si vous souhaitez procéder à l’exercice d’un ou plusieurs de ces droits, ou obtenir des informations telles que précédemment mentionnées, vous pouvez nous contacter à tout moment en adressant votre demande à l’adresse suivante : <a href="mailto:contact@sprt-society.com" class="text-yellow-400 hover:underline">contact@sprt-society.com</a>.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Nous pouvons exiger une preuve d’identité lors d’une demande d’exercice de l’un de ces droits, afin de nous assurer de ne pas altérer ou transmettre des données vous concernant à des tiers qui n’auraient pas à en connaître/ ne seraient pas habilités à solliciter une action sur ces données en votre nom.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				De manière plus générale, si vous avez des questions sur la présente Politique de protection des données ou sur la manière d’exercer vos droits, nous vous invitons à vous rapprocher du Délégué à la protection des données SPRT Society :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Par e-mail : <a href="mailto:contact@sprt-society.com" class="text-yellow-400 hover:underline">contact@sprt-society.com</a>;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Par courrier : A l’attention du Délégué à la Protection des Données, SPRT Society, 12, rue Guersant 75017, Paris , France.
				</li>
			</ul>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Si vous n’êtes pas satisfait de la façon dont nous gérons vos données personnelles, notre Délégué à la protection des données est à votre disposition pour traiter de la question directement avec vous et vous apporter les précisions nécessaires.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				Nous nous efforçons de répondre à toutes les demandes sous un mois à compter de leur réception. Cela peut cependant prendre plus de temps si la demande est particulièrement complexe ; dans cette hypothèse, vous en seriez alors averti, et la réponse vous serait adressée dans les meilleurs délais compte tenu de la nature du sujet. Pour accélérer le traitement de votre demande, nous pouvons vous demander de fournir plus de détails sur ce que vous souhaitez recevoir ou sur ce qui vous préoccupe.
			</p>
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				En cas de difficultés, ou si la réponse fournie ne vous apparait pas satisfaisante, vous disposez de la faculté de saisir la Commission Nationale de l’Informatique et des Libertés (CNIL), l’autorité locale chargée du contrôle de la protection des données personnelles afin de formuler toute réclamation :
			</p>
			<ul class="list-disc list-inside">
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					Par voie postale : CNIL - 3 place de Fontenoy - TSA 80715 - 75334 PARIS CEDEX 07;
				</li>
				<li class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4  text-justify">
					En ligne sur le site de la CNIL : <a href="https://www.cnil.fr" target="_blank" rel="noopener noreferrer" class="text-yellow-400 hover:underline">www.cnil.fr</a>.
				</li>
			</ul>
		</div>
	</div>
</section>

<section id="revision" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 pt-10 text-center">
			Révision de la présente politique
		</h2>
		<div class="flex flex-col md: items-center pt-5">
			<p class="text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify">
				La présente Politique est entrée en vigueur au 1 octobre 2025 ; elle est susceptible d’être révisée en fonction des évolutions législatives et réglementaires ou d’une modification des conditions du traitement des données personnelles.
			</p>
		</div>
	</div>
</section>

<section id="annex1" class="w-full py-20 bg-[#181818] text-white">
	<div class="w-[90%] mx-auto text-center laptop:text-right max-w-[80%]">
		<div class="bg-[#1C1C1C] rounded-lg p-4">
				<div class="flex flex-row justify-between items-center">
					<h2 class="text-base md:text-4xl text-[#F9B333] font-bold mb-6 mt-6 text-left">
						Annexe 1 : description de vos droits sur les données traitées
					</h2>
					<button class="bg-yellow-400 text-black font-bold py-2 px-4 mb-6 mt-6 rounded mb-6 hover:bg-yellow-500" on:click={() => showTab()}>
						{#if tab}Masquer l'annexe{:else}Voir l'annexe{/if}
					</button>
				</div>
				{#if tab}
				<Table>
					<TableHead>
						<TableHeadCell class="w-1/3 text-base md:text-2xl text-white font-bold text-left bg-[#1C1C1C] border border-[#F9B333]">Droit</TableHeadCell>
						<TableHeadCell class="w-2/3 text-base md:text-2xl text-white font-bold text-left bg-[#1C1C1C] border border-[#F9B333]">Qu'est-ce que cela signifie ?</TableHeadCell>
					</TableHead>
					<TableBody>
						{#each items as item}
						<TableBodyRow class="border-b border-[#F9B333]">
							<TableBodyCell class="align-top bg-[#1C1C1C] break-words whitespace-normal text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify border-b border-[#F9B333]">{item.name}</TableBodyCell>
							<TableBodyCell class="align-top bg-[#1C1C1C] break-words whitespace-normal text-xs tablet:text-gray-300 text-xl md:text-xl leading-relaxed space-y-4 mt-4 mt-10 text-justify border-b border-[#F9B333]">
								{#if Array.isArray(item.definition)}
								<ul class="list-disc list-inside space-y-2">
									{#each item.definition as def}
									<li>{def}</li>
									{/each}
								</ul>
								{:else}
								{item.definition}
								{/if}
							</TableBodyCell>
						</TableBodyRow>
						{/each}
					</TableBody>
				</Table>
				{/if}
			</div>
		</div>
</section>