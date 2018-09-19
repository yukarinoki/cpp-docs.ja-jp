---
title: リソース コンパイラ エラー RC2104 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2104
dev_langs:
- C++
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd602dcde34aa7cc08486188ab5fb5925eca0eb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081092"
---
# <a name="resource-compiler-error-rc2104"></a>リソース コンパイラ エラー RC2104

未定義のキーワードまたはキー名: キー

指定されたキーワードまたはキー名は定義されていません。

このエラーは、多くの場合、リソース定義または含まれているヘッダー ファイルの入力ミスによって発生します。 また、ヘッダー ファイルの欠落によって発生することもあります。

問題を解決するには、定義済みのキーワードまたはキー名が含まれているヘッダー ファイルを探し、それがリソース ファイルに含まれていることと、キーワードまたはキー名のスペルが正しいことを確認する必要があります。 プロジェクトがプリコンパイル済みヘッダーを使用して作成され、かつ、その後、それを削除した場合は、現在もリソース ファイルに必要なすべてのヘッダーが含まれていることを確認します。

定義のキーワードと Visual Studio で、リソース ファイル内のキー名を確認するには、開く、**リソース ビュー**ウィンドウ、メニュー バーで、**ビュー**、**リソース ビュー**: と.rc ファイルのショートカット メニューを開くし、選択**リソース シンボル**に定義されたシンボルの一覧を表示します。 含まれるヘッダーを変更するには、.rc ファイルのショートカット メニューを開くし、選択**リソース ファイルのインクルード**します。

次のメッセージが発生した場合:

```
undefined keyword or key name: MFT_STRING
```

\MCL\MFC\Include\AfxRes.h を開いて次のインクルード ディレクティブを追加します。

```
#include <winresrc.h>
```