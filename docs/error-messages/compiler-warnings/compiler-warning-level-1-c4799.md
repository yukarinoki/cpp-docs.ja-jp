---
title: コンパイラの警告 (レベル 1) C4799 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3d83917289e5ad76a874587894a66e163fed90a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088229"
---
# <a name="compiler-warning-level-1-c4799"></a>コンパイラの警告 (レベル 1) C4799

> 関数の最後にない EMM '*関数*'

関数が少なくとも 1 つの MMX 命令がありません、`EMMS`命令。 マルチ メディアの命令を使用するときに、`EMMS`命令または`_mm_empty`組み込みを使用することも MMX コードの最後に、マルチ メディア タグ単語をオフにします。

返す前に EMMS 命令 ivec.h、コードが正しく使用しないことを使用して実行時に、C4799 を取得可能性があります。 これらのヘッダーに対する警告を false になります。 オフ ivec.h で _SILENCE_IVEC_C4799 を定義することで、これらに可能性があります。 ただし、この型の正しい警告コンパイラこの保持されることもあります。

関連情報については、次を参照してください。 [Intel の MMX の命令セット](../../assembler/inline/intel-s-mmx-instruction-set.md)します。