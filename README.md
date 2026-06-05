# Dell XPS 15 9500 OpenCore Tahoe

Configuration OpenCore premium pour Dell XPS 15 9500, pensée pour une installation macOS Tahoe propre, stable et maintenable.

Ce dépôt archive une EFI complète, prête à servir de base de travail pour un XPS 15 9500 avec OpenCore. Elle inclut les ACPI, pilotes, kexts, ressources graphiques et la configuration principale nécessaires au boot.

## Aperçu

- Machine cible: Dell XPS 15 9500
- Bootloader: OpenCore
- Cible macOS: Tahoe
- SMBIOS configuré: `MacBookPro16,4`
- Dossier principal: `EFI/OC`
- Configuration: `EFI/OC/config.plist`

## Contenu

```text
EFI/
├── BOOT/
│   └── BOOTx64.efi
└── OC/
    ├── ACPI/
    ├── Drivers/
    ├── Kexts/
    ├── Resources/
    ├── Tools/
    ├── OpenCore.efi
    ├── config.plist
    └── oldConfig.plist
```

## Points forts

- Sélection complète de kexts pour audio, batterie, trackpad, Bluetooth, Wi-Fi, NVMe, capteurs SMC et gestion système.
- Ressources OpenCanopy incluses pour un boot picker soigné.
- ACPI adaptés au XPS 15 9500.
- Archive Git propre, sans fichiers système de partition EFI.

## Avant utilisation

Cette EFI est une base spécifique à une machine. Avant de l'utiliser sur un autre XPS 15 9500, vérifiez impérativement:

- `PlatformInfo`: générez vos propres valeurs SMBIOS avec GenSMBIOS ou un outil équivalent.
- `config.plist`: contrôlez les entrées ACPI, kexts et drivers avec ProperTree ou OpenCore Configurator.
- Wi-Fi/Bluetooth: adaptez les kexts selon votre carte réseau.
- NVRAM: nettoyez la NVRAM après tout changement majeur.
- Sauvegarde: gardez toujours une clé USB de secours bootable.

## Installation rapide

1. Montez la partition EFI du disque cible.
2. Copiez le dossier `EFI` à la racine de cette partition.
3. Vérifiez `EFI/OC/config.plist`.
4. Redémarrez et sélectionnez OpenCore.
5. Après validation du boot, gardez une copie de secours de cette EFI.

## Maintenance

Pour mettre à jour proprement:

1. Sauvegardez l'EFI fonctionnelle.
2. Mettez à jour OpenCore avec les binaires correspondants.
3. Mettez à jour les kexts un par un.
4. Relancez un snapshot ProperTree si nécessaire.
5. Testez sur une clé USB avant de remplacer l'EFI principale.

## Avertissement

Cette configuration est fournie comme archive personnelle et base technique. Un mauvais SMBIOS, un kext incompatible ou une configuration NVRAM incorrecte peut empêcher le démarrage. Testez toujours avant de déployer sur votre partition principale.

## Crédit

Projet maintenu par [BenDevelopment](https://github.com/BenDevelopment).

