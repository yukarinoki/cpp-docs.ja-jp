---
title: 致命的なエラー C1854 |Microsoft ドキュメント
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
ms.openlocfilehash: e517832720e31bfae88e79ad879f1427b9c25a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230248"
---
# <a name="fatal-error-c1854"></a>致命的なエラー C1854
  
> オブジェクト ファイルでプリコンパイル済みヘッダーの作成中に情報を上書きすることはできません: '*filename*'  
  
指定した、 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)オプションを指定したら、 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)同じファイル オプションを指定します。  
  
この問題を解決するを使用してコンパイルするプロジェクトで一般に、1 つのファイルを設定、 **/Yc**オプション、および設定を使用してコンパイルする他のすべてのファイル、 **/Yu**オプション。 使用に関する詳細について、 **/Yc**オプション、および Visual Studio IDE で設定する方法[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。 プリコンパイル済みヘッダーの使用の詳細については、次を参照してください。[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)です。  
