---
title: リンカー ツールの警告 LNK4247 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d84a5964cb8df5d2973b6031da55d48dade584e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078011"
---
# <a name="linker-tools-warning-lnk4247"></a>リンカー ツールの警告 LNK4247

エントリ ポイント 'decorated_function_name' は既にスレッド属性' attribute' は無視されます。

指定されたエントリ ポイントが、 [/ENTRY (エントリ ポイント シンボル)](../../build/reference/entry-entry-point-symbol.md)、スレッド属性の場合は、必要があるが、 [/CLRTHREADATTRIBUTE (CLR スレッド属性の設定)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)指定した、別のスレッド処理モデル。

リンカーでは、/CLRTHREADATTRIBUTE を指定された値が無視されます。

この警告を解決するには。

- ビルドから/CLRTHREADATTRIBUTE を削除します。

- ソース コード ファイルから属性を削除します。

- ビルドのソースと/CLRTHREADATTRIBUTE から、両方の属性を削除し、既定の CLR のスレッド モデルをそのまま使用します。

- /CLRTHREADATTRIBUTE に渡される値は、ソース内で属性に同意するように変更します。

- /CLRTHREADATTRIBUTE に渡される値とが一致するように、ソース内の属性を変更します。

次のサンプルの生成 LNK4247

```
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```