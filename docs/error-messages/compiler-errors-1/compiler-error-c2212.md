---
description: 詳細については、「コンパイラエラー C2212」を参照してください。
title: コンパイラ エラー C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: 614c93cf2c933cbdf043108c35bc06260a123ce1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245604"
---
# <a name="compiler-error-c2212"></a>コンパイラ エラー C2212

' identifier ': __based 関数へのポインターに対して使用できません

関数へのポインターを宣言することはできません **`__based`** 。 コードベースのデータが必要な場合は、 **`__declspec`** キーワードまたは `data_seg` プラグマを使用します。
