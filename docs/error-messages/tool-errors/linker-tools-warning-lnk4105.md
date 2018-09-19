---
title: リンカー ツールの警告 LNK4105 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4411421741cf8bf7c714a6322d58bd177e7e7270
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024984"
---
# <a name="linker-tools-warning-lnk4105"></a>リンカー ツールの警告 LNK4105

オプション 'option'; で指定された引数がいません。オプションを無視します

のみでこの警告が発生したときに、 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)オプションが設定されています。 このオプションでディレクトリが指定されていない、リンカーは、オプションを無視し、この警告メッセージが生成されます。

既存の環境のライブラリの設定をオーバーライドする必要がない場合は、リンカーのコマンドラインから/LIBPATH オプションを削除します。 ライブラリの別の検索パスを使用する場合は、/LIBPATH オプションに続く代替パスを指定します。

## <a name="example"></a>例

```
link /libpath:c:\filepath\lib bar.obj
```

必要なライブラリを検索するリンカーに指示が`c:\filepath\lib`の既定の場所で検索する前にします。