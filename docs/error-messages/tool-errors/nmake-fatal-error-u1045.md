---
title: NMAKE の致命的なエラー U1045 |Microsoft Docs
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
ms.openlocfilehash: c2b9be4f7440d9e79d603e917c1886aebe7c44af
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056886"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE の致命的なエラー U1045

起動に失敗しました : メッセージ

NMAKE によって呼び出されたプログラムまたはコマンドが、特定の理由により失敗しました。 NMAKE がコンパイラやリンカーなどの別のプログラムを呼び出したときに、呼び出しが失敗したか、または呼び出されたプログラムによってエラーが返された可能性があります。 このメッセージは、エラーを報告するために使用されます。

この問題を解決するには、まず、エラーの原因を判別します。 NMAKE によって報告されるコマンドを使用する[/N](../../build/nmake-options.md)オプションをコマンドラインで NMAKE によって実行されたアクションを繰り返すと、環境設定を確認します。