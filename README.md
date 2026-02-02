# Test-FinBank-app
FinBank app test
[README finbank.md](https://github.com/user-attachments/files/25017923/README.finbank.md)
# FinBank - Aplicación Bancaria

<div align="center">

![FinBank Logo](assets/icon.png)

[![React Native](https://img.shields.io/badge/React%20Native-0.81.5-blue.svg)](https://reactnative.dev/)
[![Expo](https://img.shields.io/badge/Expo-~54.0.32-black.svg)](https://expo.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-~5.9.2-blue.svg)](https://www.typescriptlang.org/)
[![License](https://img.shields.io/badge/License-Private-red.svg)]()

</div>

---

## Tabla de Contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Tecnologías](#-tecnologías)
- [Requisitos Previos](#-requisitos-previos)
- [Instalación](#-instalación)
- [Ejecución](#-ejecución)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Funcionalidades Principales](#-funcionalidades-principales)
- [Capturas de Pantalla](#-capturas-de-pantalla)
- [Arquitectura](#-arquitectura)
- [Modelos de Datos](#-modelos-de-datos)
- [API y Servicios](#-api-y-servicios)
- [Temas y Estilos](#-temas-y-estilos)
- [Desarrollo](#-desarrollo)
- [Testing](#-testing)
- [Contribución](#-contribución)
- [Autores](#-autores)
- [Licencia](#-licencia)

---

## Descripción

**FinBank** es una aplicación bancaria móvil completa desarrollada con React Native y Expo que permite a los usuarios gestionar sus cuentas bancarias, realizar transacciones y visualizar su historial financiero de manera intuitiva y segura.

La aplicación simula un entorno bancario real con funcionalidades como:
- Gestión de múltiples cuentas
- Transacciones / transferencias
- Visualización detallada de operaciones
- Generación de recibos
- Sistema de búsqueda y filtros

---

## Características

### Funcionalidades Core

- **Dashboard Principal**
  - Vista general de todas las cuentas
  - Balance total actualizado en tiempo real
  - Últimas transacciones

- **Gestión de Cuentas**
  - Múltiples cuentas (Ahorros y Corriente)
  - Soporte para diferentes monedas (DOP, USD)
  - Visualización de saldos
  - Estado de cuenta detallado

- **Transacciones Completas**
  - Transferencias entre cuentas
  - Búsqueda por descripción, monto o fecha
  - Filtros por tipo de transacción
  - Detalle completo de cada operación
  - Generación de recibos

- **Experiencia de Usuario**
  - Interfaz moderna y intuitiva
  - Animaciones fluidas
  - Diseño responsive
  - Confirmaciones visuales
  - Notificaciones de éxito/error

- **Seguridad**
  - Validación de saldos
  - Verificación de cuentas congeladas
  - Validación de datos de entrada

---

## Tecnologías

### Frontend
- **React Native** `0.81.5` - Framework principal
- **Expo** `~54.0.32` - Plataforma de desarrollo
- **TypeScript** `~5.9.2` - Tipado estático
- **Expo Router** `~6.0.22` - Navegación basada en archivos

### UI/UX
- **React Native Reanimated** `~4.1.1` - Animaciones
- **Expo Vector Icons** `^15.0.3` - Iconografía
- **Expo Linear Gradient** `~15.0.8` - Gradientes
- **React Native Safe Area Context** `~5.6.0` - Áreas seguras

### Fonts
- **JetBrains Mono** `^0.4.1` - Fuente monoespaciada
- **Outfit** `^0.4.3` - Fuente principal

### Navegación
- **React Navigation Drawer** `^7.7.13` - Menú lateral

### Desarrollo
- **Babel Preset Expo** `~54.0.10`
- **@types/react** `~19.1.0`

---

## Requisitos Previos

Antes de comenzar, asegúrate de tener instalado:

- **Node.js** (versión 18.x o superior)
- **npm** o **yarn**
- **Expo CLI** (instalado globalmente)
- **iOS Simulator** (para desarrollo en Mac) o **Android Studio** (para Android)

### Instalación de Expo CLI

```bash
npm install -g expo-cli
```

o

```bash
npm install -g @expo/cli
```


## Ejecución

### Iniciar el servidor de desarrollo

```bash
npm start
```

o

```bash
expo start
```

### Ejecutar en plataformas específicas

#### iOS
```bash
npm run ios
```

#### Android
```bash
npm run android
```

#### Web
```bash
npm run web
```

### Escanear código QR

1. Inicia el servidor con `npm start`
2. Abre la app **Expo Go** en tu dispositivo móvil
3. Escanea el código QR que aparece en la terminal

---

## Estructura del Proyecto

```
finbank/
├── app/                          # Pantallas principales (Expo Router)
│   ├── _layout.tsx              # Layout principal con navegación
│   ├── index.tsx                # Pantalla de inicio (Dashboard)
│   ├── accounts/                
│   │   └── index.tsx            # Gestión de cuentas
│   ├── transactions/            
│   │   └── index.tsx            # Lista y gestión de transacciones
│   └── settings/                
│       └── index.tsx            # Configuración de la app
│
├── components/                   # Componentes reutilizables
│   ├── header/                  # Componente de encabezado
│   ├── last-transaction-list/   # Lista de últimas transacciones
│   ├── last-transaction-list-item/ # Item individual de transacción
│   ├── stat-card/               # Tarjeta de estadísticas
│   └── typography/              # Componente de tipografía
│
├── contexts/                     # Context API de React
│   └── app-context.tsx          # Estado global de la aplicación
│
├── models/                       # Modelos de datos
│   ├── account.model.ts         # Modelo y simulación de cuentas
│   ├── profile.model.ts         # Modelo de perfiles de usuario
│   └── transaction.model.ts     # Modelo y simulación de transacciones
│
├── hooks/                        # Custom hooks
│   ├── use-accounts.ts          # Hook para gestionar cuentas
│   ├── use-profiles.ts          # Hook para gestionar perfiles
│   └── use-transactions.ts      # Hook para gestionar transacciones
│
├── theme/                        # Sistema de temas
│   ├── constants/               # Constantes de diseño
│   │   ├── colors.ts           # Paleta de colores
│   │   ├── fonts.ts            # Fuentes
│   │   ├── radius.ts           # Radios de borde
│   │   ├── shadows.ts          # Sombras
│   │   └── spacing.ts          # Espaciados
│   ├── context/                # Context del tema
│   ├── hooks/                  # Hooks del tema
│   └── utils/                  # Utilidades del tema
│
├── assets/                       # Recursos estáticos
│   ├── icon.png                # Icono de la app
│   ├── splash-icon.png         # Splash screen
│   ├── adaptive-icon.png       # Icono adaptable
│   └── favicon.png             # Favicon
│
├── app.json                      # Configuración de Expo
├── package.json                  # Dependencias y scripts
├── tsconfig.json                # Configuración de TypeScript
└── babel.config.js              # Configuración de Babel
```

---

## Funcionalidades Principales

### 1. Dashboard (Pantalla Principal)

El dashboard proporciona una vista general del estado financiero del usuario:

- **Balance Total**: Suma de todas las cuentas
- **Tarjetas de Estadísticas**: 
  - Total de ingresos
  - Total de gastos
  - Balance actual
- **Últimas Transacciones**: Vista rápida de las operaciones recientes
- **Acceso Rápido**: Navegación a otras secciones

**Ubicación**: `app/index.tsx`

### 2. Gestión de Cuentas

Permite visualizar y administrar todas las cuentas bancarias:

- Lista de todas las cuentas
- Balance individual por cuenta
- Tipo de cuenta (Ahorros/Corriente)
- Moneda (DOP/USD)
- Estado de la cuenta

**Ubicación**: `app/accounts/index.tsx`

### 3. Transacciones

Sistema completo de gestión de transacciones:

#### Crear Nueva Transacción
- Modal interactivo
- Selección de tipo (Transferencia)
- Ingreso de monto y descripción
- Selección de cuentas origen/destino
- Validación de saldos en tiempo real

#### Visualizar Transacciones
- Lista completa de todas las operaciones
- Vista detallada al hacer clic
- Información completa:
  - Monto con color según tipo
  - Fecha y hora
  - Tipo de transacción
  - Descripción
  - Cuentas involucradas
  - ID único

#### Búsqueda y Filtros
- Búsqueda por:
  - Descripción
  - Monto
  - Fecha
- Filtros por tipo:
  - Todas
  - Depósitos
  - Retiros
  - Transferencias

#### Generar Recibo
- Botón "Descargar Recibo" en cada transacción
- Recibo formateado
- Compartir vía:
  - WhatsApp
  - Email
  - SMS
  - Guardar en archivos

**Ubicación**: `app/transactions/index.tsx`

### 4. Modal de Confirmación

Al realizar una transacción exitosa:

1. Se cierra el modal de creación
2. Automáticamente se abre el detalle
3. Muestra "Transacción Exitosa"
4. Presenta toda la información
5. Permite descargar el recibo

Esto proporciona una **confirmación visual clara** de la operación.

### 5. Configuración

Ajustes:

- Preferencias de visualización
- Información de la app

**Ubicación**: `app/settings/index.tsx`

---

## Capturas de Pantalla

### Dashboard
```
┌──────────────────────────────────┐
│  FinBank         [≡]  [☾]  [👤] │
├──────────────────────────────────┤
│  Balance Total                   │
│  $34,000.00                      │
├──────────────────────────────────┤
│  [Ingresos] [Gastos]             │
│  [Balance]                       │
├──────────────────────────────────┤
│  Últimas Transacciones           │
│  ┌────────────────────────────┐  │
│  │ Depósito    +$1,200.00     │  │
│  │ → ahorros (USD)            │  │
│  │ 2 de febrero               │  │
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

### Transacciones
```
┌──────────────────────────────────┐
│  Transacciones  [📤][🔍][➕Nueva]│
├──────────────────────────────────┤
│  [Todas][Depósitos][Retiros]     │
│  [Transferencias]                │
├──────────────────────────────────┤
│  ┌────────────────────────────┐  │
│  │ 💹 Depósito   +$500.00    │  │
│  │ → ahorros (USD)           │  │
│  │ 15 ene                    │  │
│  └────────────────────────────┘  │
│  ┌────────────────────────────┐  │
│  │ ↗️ Transferencia  $300.00  │  │
│  │ corriente (DOP)→ahorros   │  │
│  │ 10 ene                    │  │
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

### Detalle de Transacción
```
┌──────────────────────────────────┐
│  ✓ Transacción Exitosa      [X] │
│     💹 depósito                  │
├──────────────────────────────────┤
│            Monto                 │
│         +$500.00                 │
├──────────────────────────────────┤
│  📅 Fecha                        │
│     2 de febrero de 2026, 01:00 │
│                                  │
│  📑 Tipo                         │
│     Depósito                     │
│                                  │
│  💰 Cuenta Destino               │
│     ahorros (USD) - $2000.00    │
│                                  │
│  🏷️ ID: 1234567890              │
├──────────────────────────────────┤
│  [📥 Descargar Recibo]          │
│  [      Cerrar      ]           │
└──────────────────────────────────┘
```

---

## Arquitectura

### Patrón de Diseño

FinBank utiliza una arquitectura basada en:

1. **Component-Based Architecture**: Componentes reutilizables y modulares
2. **Context API**: Gestión de estado global
3. **File-Based Routing**: Navegación con Expo Router
4. **Model Layer**: Separación de lógica de datos
5. **Theme System**: Sistema centralizado de estilos

### Flujo de Datos

```
Usuario Interactúa
       ↓
  Componente UI
       ↓
   Context API (app-context.tsx)
       ↓
  Modelos (Models)
       ↓
  Actualización de Estado
       ↓
  Re-render de UI
```

### Context API

El estado global se gestiona mediante React Context:

**`app-context.tsx`** proporciona:
- Estado de cuentas
- Estado de transacciones
- Funciones de actualización
- Estado de carga

```typescript
interface AppContextType {
  
  // Accounts
  accounts: Account[];
  updateAccountBalance: (id: string, balance: number) => void;
  
  // Transactions
  transactions: Transaction[];
  addTransaction: (transaction: Omit<Transaction, "id" | "date">) => void;
  
  // Loading
  isLoading: boolean;
}
```

---

## Modelos de Datos

### Account (Cuenta)

```typescript
interface Account {
  id: string;
  type: AccountType;        // "ahorros" | "corriente"
  currency: AccountCurrency; // "DOP" | "USD"
  balance: number;
  ownerId: string;
}
```

**Tipos de Cuenta:**
- `SAVINGS` (Ahorros)
- `CHECKING` (Corriente)

**Monedas:**
- `DOP` (Peso Dominicano)
- `USD` (Dólar Estadounidense)

### Transaction (Transacción)

```typescript
interface Transaction {
  id: string;
  type: TransactionType;    // "transferencia"
  amount: number;
  description: string;
  date: Date;
  fromAccountId: string;
  toAccountId: string;
}
```

**Tipos de Transacción:**
- `TRANSFER` (Transferencia)

### Profile (Perfil)

```typescript
interface Profile {
  id: string;
  name: string;
  email: string;
  avatar: string | null;
}
```

---

## API y Servicios

### Simulación de Datos

La aplicación utiliza datos simulados almacenados localmente en los modelos.

**AccountModel**
```typescript
static async findMany(): Promise<Account[]>
static async findById(id: string): Promise<Account | null>
```

**TransactionModel**
```typescript
static async findMany(): Promise<Transaction[]>
static async findById(id: string): Promise<Transaction | null>
```

**ProfileModel**
```typescript
static async findMany(): Promise<Profile[]>
static async findById(id: string): Promise<Profile | null>
```

Todas las operaciones incluyen un `setTimeout` de 2 segundos para simular latencia de red.

### Funciones de Negocio

#### Validación de Transacciones

```typescript
// Validar saldo suficiente
if (fromAccount.balance < amount) {
  throw new Error("Saldo insuficiente");
}

// Validar cuenta no congelada
if (fromAccount.isFrozen) {
  throw new Error("Cuenta congelada");
}
```

#### Actualización de Balances

```typescript

// Transferencia
fromAccount.balance -= amount;
toAccount.balance += amount;
```

---

## Temas y Estilos

### Sistema de Temas

FinBank implementa un sistema de temas que soporta:

- Cambio dinámico sin recargar

### Paleta de Colores

#### Colores por Tipo de Transacción
```typescript
const transactionColors = {
  deposit: "#10B981",     // Verde
  withdrawal: "#EF4444",  // Rojo
  transfer: "#3B82F6",    // Azul
};
```

#### Colores de Fondo
```typescript
colors: {
  background: {
    "bg-color-base": string,
    "bg-color-secondary": string,
    "bg-color-accent": string,
  }
}
```

#### Colores de Texto
```typescript
colors: {
  text: {
    "text-color-main": string,
    "text-color-secondary": string,
  }
}
```

### Espaciado

```typescript
spacing: {
  s1: 4,
  s2: 8,
  s3: 12,
  s4: 16,
  s5: 20,
  s6: 24,
  s7: 28,
  s8: 32,
}
```

### Radios

```typescript
radius: {
  r1: 4,
  r2: 8,
  r3: 12,
  r4: 16,
  r5: 20,
}
```

### Tipografía

**Fuentes:**
- Principal: **Outfit** (400, 500, 600, 700)
- Monoespaciada: **JetBrains Mono**

**Variantes:**
- `h1`: 32px, bold
- `h2`: 24px, bold
- `h3`: 20px, semibold
- `h4`: 16px, medium
- `body`: 14px, regular
- `caption`: 12px, regular

---

## Desarrollo

### Agregar Nueva Pantalla

1. Crear archivo en `app/nueva-pantalla/index.tsx`
2. Implementar el componente
3. Expo Router lo detectará automáticamente

```typescript
// app/nueva-pantalla/index.tsx
export default function NuevaPantalla() {
  return (
    <View>
      <Text>Nueva Pantalla</Text>
    </View>
  );
}
```

### Crear Nuevo Componente

```typescript
// components/mi-componente/index.tsx
import { View, Text } from 'react-native';
import { useTheme } from '@/theme';

export function MiComponente() {
  const { palette } = useTheme();
  
  return (
    <View>
      <Text style={{ color: palette.colors.text["text-color-main"] }}>
        Mi Componente
      </Text>
    </View>
  );
}
```

### Agregar Nueva Transacción

```typescript
const { addTransaction } = useAppContext();

addTransaction({
  type: TransactionType.DEPOSIT,
  amount: 100,
  description: "Depósito",
  fromAccountId: "0",
  toAccountId: "1",
});
```

### Usar el Tema

```typescript
import { useTheme } from '@/theme';

function MiComponente() {
  const { palette, spacing, radius } = useTheme();
  
  return (
    <View style={{
      backgroundColor: palette.colors.background["bg-color-base"],
      padding: spacing.s4,
      borderRadius: radius.r3,
    }}>
      {/* contenido */}
    </View>
  );
}
```

---

## Testing

### Ejecutar Tests

```bash
npm test
```

### Estructura de Tests

```
__tests__/
├── components/
├── models/
├── hooks/
└── utils/
```

### Ejemplo de Test

```typescript
describe('TransactionModel', () => {
  it('should fetch all transactions', async () => {
    const transactions = await TransactionModel.findMany();
    expect(transactions.length).toBeGreaterThan(0);
  });
});
```

---


## Recursos Adicionales

### Documentación
- [React Native Docs](https://reactnative.dev/docs/getting-started)
- [Expo Docs](https://docs.expo.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)

---

## Changelog

### Version 1.0.0 (2026-02-02)

#### Características 
- Sistema completo de transacciones
- Modal de detalle de transacción
- Generación de recibos
- Búsqueda y filtros avanzados
- Confirmación visual de operaciones

#### UI
- Diseño moderno y limpio
- Animaciones fluidas
- Iconografía consistente
- Responsive design

---

<div align="center">

**Hecho por Julianny Tejeda**

[⬆ Volver arriba](#-finbank---aplicación-bancaria-móvil)

</div>
