---
title: カスタム ビルド ステップまたはビルド イベントの出力を書式設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7da71e6391d2d3223b47ba528686d2fec003ab3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>カスタム ビルド ステップまたはビルド イベントの出力の書式設定
カスタム ビルド ステップまたはビルド イベントの出力の形式が正しく、ユーザーは、次の利点を取得します。  
  
-   警告とエラーにカウントされて、**出力**ウィンドウです。  
  
-   出力に表示されます、**タスク一覧**ウィンドウです。  
  
-   出力でをクリックすると、**出力**ウィンドウには、該当するトピックが表示されます。  
  
-   F1 キー操作が有効になっている、**タスク一覧**ウィンドウまたは**出力**ウィンドウです。  
  
 出力の形式にする必要があります。  
  
 {*filename* (*行番号*[、*列 #*]) &#124; *toolname*} **:**  
  
 [*任意のテキスト*] {**エラー** &#124; **警告**}*コード ###***:*** ローカライズ可能な文字列*  
  
 [*任意のテキスト*]  
  
 この場合、  
  
-   {*、* &#124; *b*} は、いずれかの選択肢*、*または*b*です。  
  
-   [`ccc`] は省略可能な文字列またはパラメーターです。  
  
 例えば:  
  
 C:\\*sourcefile.cpp*(134): エラー C2143: 構文エラー: 見つかりません ';' は、前に '}'  
  
 リンク: 致命的なエラー LNK1104: ファイルを開くことができません '*somelib.lib*'  
  
## <a name="see-also"></a>関連項目  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)