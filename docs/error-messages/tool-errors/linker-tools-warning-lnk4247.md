---
title: リンカー ツールの警告 LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: cd4108f8bd06ec7a0b2d2eb9fab13917174b797b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346961"
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