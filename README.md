# SIF-Amir: Contabilidad para Persona Física

Módulo contable exclusivo para **Amir Tafreshi** (Persona Física).

## 📋 Contenido

- **index.html** - Módulo principal (tabs: Catálogo, Balanzas, Estados Financieros, Ratios, Pólizas)
- **sql_setup.sql** - Script de creación de tablas Supabase + carga de 1,080 cuentas

## 🚀 Setup

### Paso 1: Ejecutar SQL en Supabase

1. Abre **Supabase Console** → `nzrzrbatcmzcmrmyrama.supabase.co`
2. Ve a **SQL Editor**
3. Copia el contenido de `sql_setup.sql` y pégalo en el editor
4. Ejecuta (▶️)
5. Espera confirmación: "CREATE TABLE", "INSERT 1080"

### Paso 2: Crear Repo GitHub

1. Ve a github.com/JCGT1976
2. Crea nuevo repo `Amir` (descripción: "SIF Contabilidad - Persona Física Amir")
3. No inicialices con README (vacío)
4. Copia los 3 archivos (`index.html`, `sql_setup.sql`, `README.md`)
5. Haz push a main

### Paso 3: Configurar SIF-Portal

En SIF-Portal, agrega una nueva tarjeta:
- **Nombre**: "Amir"
- **URL**: `https://raw.githubusercontent.com/JCGT1976/Amir/main/index.html`
- **Icono**: 📊

## 🎯 Tabs del Módulo

| Tab | Función |
|-----|---------|
| 📋 Catálogo | Ver/buscar 1,080 cuentas; importar Excel |
| ⚖️ Balanzas | Generar balanzas de comprobación por fecha |
| 📑 Estados | Balance General, Estado de Resultados, EFE |
| 📈 Ratios | Liquidez, Rentabilidad, Endeudamiento |
| 🔐 Pólizas | Crear pólizas (Ingreso/Egreso/Diario); historial |

## 🗂️ Tablas Supabase

```
amir_catalogo_cuentas (1080 registros)
├─ id, codigo, nombre, tipo, nivel, nif, agrupador_sat, created_at

amir_polizas
├─ id, fecha, tipo_poliza, numero, concepto, created_by, created_at

amir_polizas_detalles
├─ id, poliza_id, cuenta_id, debe, haber, created_at
```

## 📌 Notas

- **Acceso**: Solo JC (admin_master)
- **Catálogo**: Basado en ContPAQ i de Amir (30/Abr/2026)
- **APP_VERSION**: v2026.08.13.1 (bump automático en cada push)
- **Verifier**: Ejecutar deadpool-verifier antes de cada push

## 🔄 Flujo de Desarrollo

1. Edita `index.html`
2. Prueba localmente
3. Bumpa APP_VERSION en formato `YYYY.MM.DD.N`
4. Haz push a main (`git push`)
5. Verifica en SIF-Portal (auto-update)

---

**Catálogo**: 1,080 cuentas completas (Activos, Pasivos, Capital, Resultados, Orden)  
**Última actualización**: 13/Ago/2026  
**Estado**: Fase 1 (Catálogo + Structure); Fase 2 (Pólizas full) en desarrollo
