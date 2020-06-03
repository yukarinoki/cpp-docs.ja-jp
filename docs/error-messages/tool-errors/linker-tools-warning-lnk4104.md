---
title: リンカー ツールの警告 LNK4104
ms.date: 11/04/2016
f1_keywords:
- LNK4104
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
ms.openlocfilehash: 604dccf01b3dffc0060546bebf19d64c16ebf965
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193967"
---
# <a name="linker-tools-warning-lnk4104"></a>リンカー ツールの警告 LNK4104

シンボル ' symbol ' のエクスポートはプライベートでなければなりません

`symbol` には、次のいずれかを指定できます。

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

この警告は、DLL のインポートライブラリを作成し、上記の関数のいずれかをモジュール定義ファイルで PRIVATE として指定せずにエクスポートしたときに生成されます。 一般に、これらの関数は OLE でのみ使用するためにエクスポートされます。 これらのファイルをインポートライブラリに配置すると、ライブラリにリンクしているプログラムが誤って呼び出しを行った場合に、異常な動作が発生する可能性があります。 PRIVATE キーワードの詳細については、「[エクスポート](../../build/reference/exports.md)」を参照してください。
