---
title: NMAKE の致命的なエラー U1045 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673b20dde7156025c6aa56c487433eebe9e77aa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316375"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE の致命的なエラー U1045
起動に失敗しました : メッセージ  
  
 NMAKE によって呼び出されたプログラムまたはコマンドが、特定の理由により失敗しました。 NMAKE がコンパイラやリンカーなどの別のプログラムを呼び出したときに、呼び出しが失敗したか、または呼び出されたプログラムによってエラーが返された可能性があります。 このメッセージは、エラーを報告するために使用されます。  
  
 この問題を解決するには、まず、エラーの原因を判別します。 NMAKE によって報告されるコマンドを使用する[/N](../../build/nmake-options.md)オプション環境設定を確認して、コマンドラインで NMAKE によって実行される操作を繰り返します。