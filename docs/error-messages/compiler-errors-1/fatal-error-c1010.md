---
title: 致命的なエラー C1010 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae762c15c96ed7c12a20d2070d22cdc556667ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064088"
---
# <a name="fatal-error-c1010"></a>致命的なエラー C1010

プリコンパイル ヘッダーを検索中に不明な EOF が見つかりました。 追加を忘れました ' # 名 include' ソースにでしょうか。

指定されたインクルード ファイル[/Yu](../../build/reference/yu-use-precompiled-header-file.md)はソース ファイルに表示されません。  このオプションは既定ではほとんどの Visual C プロジェクトの種類で有効にして、"stdafx.h"が既定値は、このオプションで指定されたファイルを含めます。

Visual Studio 環境でこのエラーを解決するのには、次のメソッドのいずれかを使用します。

- プロジェクトでプリコンパイル済みヘッダーを使用しない場合は、設定、**プリコンパイル済みヘッダーの作成/使用**するソース ファイルのプロパティ**プリコンパイル済みヘッダーを使用して**します。 このコンパイラ オプションを設定するには、次の手順を実行します。

   1. プロジェクトの [ソリューション エクスプ ローラー] ウィンドウで、プロジェクト名を右クリックし、**プロパティ**します。

   1. 左側のウィンドウでをクリックして、 **C/C++** フォルダー。

   1. をクリックして、**プリコンパイル済みヘッダー**ノード。

   1. 右側のウィンドウで次のようにクリックします。**プリコンパイル済みヘッダーの作成/使用**、 をクリックし、**プリコンパイル済みヘッダーを使用しない**します。

- 誤って削除、名前変更、またはヘッダー ファイルを削除するかどうかを確認 (既定では、stdafx.h) 現在のプロジェクトから。 このファイルも含める必要があるその他のコードを使用して、ソース ファイル内の前に **#"stdafx.h"を include**します。 (としてこのヘッダー ファイルが指定された**ファイルを使用して PCH を作成/使用**プロジェクトのプロパティ)