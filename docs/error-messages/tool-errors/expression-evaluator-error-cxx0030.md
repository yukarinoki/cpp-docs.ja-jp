---
title: 式エバリュエーター エラー CXX0030 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2921013d116b7d8f02e1e29380ca3cd14086b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102815"
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030

評価できない式

書き込まれると、デバッガーの式エバリュエーターは式の値を取得できませんでした。 1 つの原因と考えられますが、式がプログラムのアドレス空間外のメモリを指すこと (1 つの例では null ポインターの逆参照)。 Windows では、プログラムのアドレス空間の外部では、メモリにアクセスをできません。

評価の順序を制御するかっこを使用して、式を書き直してくださいたい場合があります。

このエラーは、can0030 と同じものと同じです。