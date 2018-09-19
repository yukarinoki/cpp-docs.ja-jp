---
title: assert 関数によって出力される診断 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e824e94f79aa01ab3a82675fb3e8f76059c567d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195553"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert 関数によって出力される診断
**ANSI 4.2** **assert** 関数が印刷する診断と関数の終了動作  
  
**assert** 関数は診断メッセージを表示し、式が false (0) の場合に **abort** ルーチンを呼び出します。 診断メッセージにフォームがあります  

> **アサーションに失敗しました**: <em>expression</em>**, ファイル** <em>filename</em>**, 行** *linenumber*  

ここで、*filename* はソース ファイルの名前であり、*linenumber* はソース ファイルで失敗したアサーションの行番号です。 *expression* が true の場合 (ゼロ以外)、アクションは発生しません。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)