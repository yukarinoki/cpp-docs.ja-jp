---
description: 詳細については、「リンカーツールの警告 LNK4104」を参照してください。
title: リンカー ツールの警告 LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: ab48885a4a8d2806154d3a8911bdc65453359e2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294432"
---
# <a name="linker-tools-warning-lnk4104"></a>リンカー ツールの警告 LNK4104

シンボル ' symbol ' のエクスポートはプライベートでなければなりません

には、 `symbol` 次のいずれかを指定できます。

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

この警告は、DLL のインポートライブラリを作成し、上記の関数のいずれかをモジュール定義ファイルで PRIVATE として指定せずにエクスポートしたときに生成されます。 一般に、これらの関数は OLE でのみ使用するためにエクスポートされます。 これらのファイルをインポートライブラリに配置すると、ライブラリにリンクしているプログラムが誤って呼び出しを行った場合に、異常な動作が発生する可能性があります。 PRIVATE キーワードの詳細については、「 [エクスポート](../../build/reference/exports.md)」を参照してください。
