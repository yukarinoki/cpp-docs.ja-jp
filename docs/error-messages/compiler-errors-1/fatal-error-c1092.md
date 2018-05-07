---
title: 致命的なエラー C1092 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8f5b5d903fe1fb2d3182a7b08f7bf82ddf334fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092
エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。  
  
 前回成功したビルド以降、データ型を追加または変更します。  
  
-   エディット コンティニュは、クラス、構造体、または列挙型の定義を含む既存のデータ型への変更をサポートしていません。 デバッグを停止し、アプリケーションをビルドする必要があります。  
  
-   エディット コンティニュが場合 vc などのプログラム データベース ファイルの新しいデータ型の追加をサポートしていません*x*0 pdb (ここで*x*メジャー バージョンの Visual C の使用) は読み取り専用です。 データ型を追加するには、コンパイラは、書き込みモードで .pdb ファイルを開く必要があります。  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこのエラーを削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **[デバッグ]** メニューの **[コード変更を適用]** をクリックします。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには  
  
1.  **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。  
  
2.  **[ビルド]** メニューの **[ビルド]** をクリックします。  
  
 詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。