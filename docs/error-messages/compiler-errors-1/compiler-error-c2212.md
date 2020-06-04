---
title: コンパイラ エラー C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: bf478c96e76a4fe139caee79f497a0abe7f70824
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206682"
---
# <a name="compiler-error-c2212"></a>コンパイラ エラー C2212

' identifier ': __based 関数へのポインターに対して使用できません

関数へのポインターを `__based`として宣言することはできません。 コードベースのデータが必要な場合は、`__declspec` キーワードまたは `data_seg` プラグマを使用します。
