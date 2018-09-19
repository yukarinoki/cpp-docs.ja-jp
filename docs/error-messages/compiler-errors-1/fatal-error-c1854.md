---
title: 致命的なエラー C1854 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1854
dev_langs:
- C++
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83450169ec928bb77e46916619c84b3b9a3443a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029391"
---
# <a name="fatal-error-c1854"></a>致命的なエラー C1854

> オブジェクト ファイルでプリコンパイル済みヘッダーの作成中に情報を上書きすることはできません: '*filename*'

指定した、 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)オプションを指定した後、 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)同じファイル オプションを指定します。

この問題を解決するを使用してコンパイルするプロジェクトで一般に、1 つのファイルを設定、 **/Yc**オプション、およびその他のすべてのファイルを使用してコンパイルする設定、 **/Yu**オプション。 詳細については、使用するときの **/Yc**オプション、および Visual Studio IDE で設定を参照してください方法[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)。 プリコンパイル済みヘッダーの使用の詳細については、次を参照してください。[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)です。
