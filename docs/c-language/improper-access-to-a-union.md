---
title: 共用体への不適切なアクセス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac723ed80eaebc4b3f245ef56b761600007cd2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028377"
---
# <a name="improper-access-to-a-union"></a>Improper Access to a Union (共用体への不適切なアクセス)

**ANSI 3.3.2.3** 共用体オブジェクトのメンバーが異なる型のメンバーを使用してアクセスされます

2 の型の 1 つの共用体が宣言され、一方の値が格納されていても、もう一方の型で共用体にアクセスできる場合、結果は信頼できません。

たとえば、**float** と `int` の共用体が宣言されます。 **float** 値が保存されますが、プログラムは `int` として値にアクセスします。 このような場合、値は **float** 値の内部ストレージによって異なります。 整数値は信頼できません。

## <a name="see-also"></a>参照

[構造体、共用体、列挙体、ビット フィールド](../c-language/structures-unions-enumerations-and-bit-fields.md)