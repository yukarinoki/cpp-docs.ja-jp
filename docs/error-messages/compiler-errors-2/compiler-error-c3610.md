---
description: 詳細については、「コンパイラエラー C3610」を参照してください。
title: コンパイラ エラー C3610
ms.date: 11/04/2016
f1_keywords:
- C3610
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
ms.openlocfilehash: 0fca8f57fcdf2e935620118092708ba1c94f5ec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223140"
---
# <a name="compiler-error-c3610"></a>コンパイラ エラー C3610

' valuetype ': メソッド ' method ' を呼び出すことができるようにするには、値の型を ' ボックス化 ' にする必要があります

既定では、値型はマネージヒープ上にありません。 などの .NET ランタイムクラスからメソッドを呼び出すには、その前に、 `Object` 値型をマネージヒープに移動する必要があります。

C3610 は、互換性のために残されているコンパイラオプション **/clr: oldSyntax** を使用してのみ到達可能です。
