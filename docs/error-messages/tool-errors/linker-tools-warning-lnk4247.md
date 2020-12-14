---
description: 詳細については、「リンカーツールの警告 LNK4247」を参照してください。
title: リンカー ツールの警告 LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 88cd04e345b798b6927c3a5297380f1eeb3c5f5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241184"
---
# <a name="linker-tools-warning-lnk4247"></a>リンカー ツールの警告 LNK4247

エントリポイント ' decorated_function_name ' には既にスレッド属性があります。' attribute ' が無視されました

[/Entry (エントリポイントシンボル)](../../build/reference/entry-entry-point-symbol.md)で指定されたエントリポイントにはスレッド属性がありますが、別のスレッドモデルで[/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)も指定されていました。

リンカーは、/clrthreadattributeで指定された値を無視しました。

この警告を解決するには:

- ビルドから/CLRTHREADATTRIBUTE を削除します。

- ソースコードファイルから属性を削除します。

- ソースと/CLRTHREADATTRIBUTE から属性を両方ともビルドから削除し、既定の CLR スレッド処理モデルを受け入れます。

- /CLRTHREADATTRIBUTE に渡される値を変更します。これにより、source の属性に同意したことになります。

- Source の属性を変更します。これは、/clrthreadattributeに渡された値に同意します。

次の例では、LNK4247 が生成されます。

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
