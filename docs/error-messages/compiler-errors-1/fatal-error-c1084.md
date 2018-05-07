---
title: 致命的なエラー C1084 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7266a2158c3e6ccd02ea82de22c6f90a8b6363d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1084"></a>致命的なエラー C1084
filetype ファイルを読み取れません。'file': message  
  
 このエラーは一般的に、コンパイラによって行われた内部的なシステム API 呼び出しの失敗によって発生します。 このエラーが発生したときに表示されるメッセージはいずれかで生成されることが[_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)または[FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx)です。  
  
 次の手順を実行すると、C1084 の解決に役立つ場合があります。  
  
-   指定したファイルが存在することを確認します。  
  
-   指定したファイルにアクセスするための適切なアクセス許可が設定されていることを確認します。  
  
-   コマンドラインの構文ルールに準拠するに記載されていることを確認[コンパイラのコマンドライン構文](../../build/reference/compiler-command-line-syntax.md)です。  
  
-   環境変数を確認**TMP**と**TEMP**は、正しくセットとこれらの環境変数が指すディレクトリにアクセスするために適切なアクセス許可。 によって参照されているドライブも確認、 **TMP**と**TEMP**環境変数には、十分な量空き領域にはが含まれています。  
  
-   "ファイル番号が正しくありません" というメッセージが表示される場合は、指定したファイルがバックグラウンドでのコンパイル中にフォアグラウンドで閉じられている可能性があります。  
  
 上記の診断を実行した後、クリーン ビルドを実行します。