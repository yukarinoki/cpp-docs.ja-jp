---
title: リンカー ツールの警告 LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 655a6dfde77984cd0c941ec0d8abb0c4d099c80f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183294"
---
# <a name="linker-tools-warning-lnk4105"></a>リンカー ツールの警告 LNK4105

オプション ' option ' で引数が指定されていません。オプションを無視する

この警告は、 [/libpath](../../build/reference/libpath-additional-libpath.md)オプションが設定されている場合にのみ発生します。 このオプションを使用してディレクトリが指定されていない場合、リンカーはオプションを無視し、この警告メッセージを生成します。

既存の環境ライブラリ設定を上書きする必要がない場合は、リンカーコマンドラインから/LIBPATH オプションを削除します。 ライブラリに別の検索パスを使用する場合は、/LIBPATH オプションの後に代替パスを指定します。

## <a name="example"></a>例

```
link /libpath:c:\filepath\lib bar.obj
```

は、既定の場所を検索する前に、`c:\filepath\lib` で必要なライブラリを検索するようにリンカーに指示します。
