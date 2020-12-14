---
description: 詳細については、「リンカーツールの警告 LNK4222」を参照してください。
title: リンカー ツールの警告 LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 215dd04339b783d558b05140bb7dd08c5936d5e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222608"
---
# <a name="linker-tools-warning-lnk4222"></a>リンカー ツールの警告 LNK4222

エクスポートされたシンボル ' symbol ' に序数を割り当てることはできません

次のシンボルは、序数でエクスポートしないでください。

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

これらの関数は、常にを使用して名前によって検索され `GetProcAddress` ます。 リンカーは、この種類のエクスポートに関する警告を表示します。これは、イメージのサイズが大きくなる可能性があるためです。 これは、序数エクスポートの範囲が比較的少ないエクスポートで大きい場合に発生する可能性があります。 たとえば、次のように入力します。

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

では、エクスポートアドレステーブルに98が含まれている100スロットが必要です (2-99)。 反対に

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

2つのスロットが必要です。 (また、 [/export](../../build/reference/export-exports-a-function.md) リンカーオプションを使用してエクスポートすることもできます)。
