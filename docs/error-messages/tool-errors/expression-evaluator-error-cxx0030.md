---
title: 式エバリュエーター エラー CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 1e52b238905fba5c310a89377b81548a1c6b5784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500348"
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030

評価できない式

書き込まれると、デバッガーの式エバリュエーターは式の値を取得できませんでした。 1 つの原因と考えられますが、式がプログラムのアドレス空間外のメモリを指すこと (1 つの例では null ポインターの逆参照)。 Windows では、プログラムのアドレス空間の外部では、メモリにアクセスをできません。

評価の順序を制御するかっこを使用して、式を書き直してくださいたい場合があります。

このエラーは、can0030 と同じものと同じです。