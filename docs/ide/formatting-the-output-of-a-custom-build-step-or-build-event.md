---
title: カスタム ビルド ステップまたはビルド イベントの出力の書式設定 | Microsoft Docs
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33321351"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>カスタム ビルド ステップまたはビルド イベントの出力の書式設定
カスタム ビルド ステップまたはビルド イベントの出力形式が正しい場合、ユーザーには次の利点があります。  
  
-   警告とエラーが、**[出力]** ウィンドウにカウントされます。  
  
-   出力が、**[タスク一覧]** ウィンドウに表示されます。  
  
-   **[出力]** ウィンドウの出力をクリックすると、該当するトピックが表示されます。  
  
-   **[タスク一覧]** ウィンドウまたは **[出力]** ウィンドウでは、F1 キーの操作を使用できます。  
  
 出力形式は、次のとおりです。  
  
 {*<ファイル名>* (*<行番号>* [, *<列番号>*]) &#124; *<ツール名>*} **:**  
  
 [*<任意のテキスト>*] {**<エラー>** &#124; **<警告>**} *<コード番号>***:***<ローカライズ可能な文字列>*  
  
 [ *<任意のテキスト>* ]  
  
 この場合、  
  
-   {*a* &#124; *b*} には、*a* または *b* を選択します。  
  
-   [`ccc`] は任意の文字列またはパラメーターです。  
  
 例:  
  
 C:\\*sourcefile.cpp*(134) : エラー C2143: 構文エラー: ';' が '}' の前にありません  
  
 LINK : 致命的なエラー LNK1104: '*somelib.lib*' を開くことができません。  
  
## <a name="see-also"></a>参照  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)