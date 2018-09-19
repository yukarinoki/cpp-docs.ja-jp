---
title: リンカー ツールの警告 LNK4104 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6304f3ea928c89f4756a4594270ebb7914324f85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057263"
---
# <a name="linker-tools-warning-lnk4104"></a>リンカー ツールの警告 LNK4104

シンボル 'symbol' のエクスポートがプライベートにする必要があります。

`symbol`次のいずれかを指定できます。

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllGetDocumentation`

- `DllInitialize`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllRegisterServerExW`

- `DllUnload`

- `DllUnregisterServer`

- `RasCustomDeleteEntryNotify`

- `RasCustomDial`

- `RasCustomDialDlg`

- `RasCustomEntryDlg`

この警告は、dll インポート ライブラリを構築するときに生成され、モジュール定義ファイル内のプライベートとして指定せずに、上記の関数のいずれかをエクスポートします。 一般に、これらの関数は、OLE でのみ使用するためエクスポートされます。 リンクされているライブラリを正しくプログラムがそれらへの呼び出しを行うと、インポート ライブラリに配置するは異常な動作につながります。 PRIVATE キーワードの詳細については、次を参照してください。[エクスポート](../../build/reference/exports.md)します。