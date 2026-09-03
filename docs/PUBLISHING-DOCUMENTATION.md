# Activar el README visual en Marketplace

El paquete entregado incluye dos READMEs:

- `README.md`: versión segura para empaquetar **sin** `package.json.repository`.
- `README-MARKETPLACE-VISUAL.md`: versión con galería completa de imágenes y enlaces a `docs/`.

## ¿Por qué existen dos?

VSCE reescribe enlaces e imágenes relativas cuando empaqueta una extensión. Para hacerlo necesita saber cuál es el repositorio remoto. El ZIP recibido no contiene una URL `repository` verificable y no se inventó una.

## Cuando tengas la URL GitHub definitiva

1. Agrega a `package.json`:

```json
"repository": {
  "type": "git",
  "url": "https://github.com/ORGANIZACION/REPOSITORIO.git"
}
```

2. Sustituye el ejemplo por la URL real.
3. Completa las capturas indicadas en `SCREENSHOT-PLAYBOOK.md`.
4. Copia `README-MARKETPLACE-VISUAL.md` sobre `README.md`.
5. Ejecuta:

```bash
npm install
npm run verify
npm run package:release
```

6. Abre el VSIX o súbelo como actualización en Marketplace.

## Checklist antes de publicar la documentación visual

- [ ] `package.json.repository` apunta al repositorio real.
- [ ] Todas las imágenes existen.
- [ ] No hay passwords, IPs sensibles o datos privados en capturas.
- [ ] `npm run verify` termina con Exit code 0.
- [ ] `vsce package` no reporta enlaces relativos inválidos.
- [ ] README se ve bien en GitHub.
- [ ] README se ve bien en Marketplace preview.
