---
description: 詳細については、「NMAKE の致命的なエラー U1045」を参照してください。
title: NMAKE の致命的なエラー U1045
ms.date: 08/11/2019
f1_keywords:
- U1045
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
ms.openlocfilehash: 722525d917b7511dfe2294adf2e796efd3078913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322896"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE の致命的なエラー U1045

> 起動に失敗しました: *メッセージ*

NMAKE によって呼び出されたプログラムまたはコマンドが、 *メッセージ* の理由により失敗しました。 NMAKE がコンパイラやリンカーなどの別のプログラムを呼び出すと、呼び出しが失敗する可能性があります。 または、呼び出されたプログラムによってエラーが返される場合があります。 このメッセージは、エラーを報告するために使用されます。

この問題を解決するには、まず、エラーの原因を判別します。 NMAKE [/n](../../build/reference/running-nmake.md#nmake-options) オプションによって報告されたコマンドを使用して、環境設定を確認し、コマンドラインで nmake によって実行された操作を繰り返すことができます。
