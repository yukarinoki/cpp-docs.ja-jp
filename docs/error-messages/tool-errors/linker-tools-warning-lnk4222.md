---
title: リンカー ツールの警告 LNK4222 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abc4f85fbc361b37d9325f9d395a1c34e1eeed2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106933"
---
# <a name="linker-tools-warning-lnk4222"></a>リンカー ツールの警告 LNK4222

エクスポートされたシンボル 'symbol' に序数を割り当てないでください。

次の記号は、序数でエクスポートする必要がありません。

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

これらの関数は常に名前であるを使用して`GetProcAddress`します。 リンカーはこれについて警告エクスポートの種類と拡大画像が生じる可能性があるためです。 これは、序数でのエクスポートの範囲が比較的少ないエクスポートを含む大規模な場合に発生する可能性があります。 たとえば、オブジェクトに適用された

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

100 のうち 98 にエクスポート アドレス テーブル (2 ~ 99) は単なる空白スロットを必要となります。 一方

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

2 つのスロットを必要となります。 (にもエクスポートできることに注意してください、 [/export](../../build/reference/export-exports-a-function.md)リンカー オプション)。