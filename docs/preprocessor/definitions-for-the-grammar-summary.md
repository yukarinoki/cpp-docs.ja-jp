---
title: 文法の概要での定義
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 6e8671ba0d68b13f68db0f2b08dab4fe98f917e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024956"
---
# <a name="definitions-for-the-grammar-summary"></a>文法の概要での定義

終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。

非終端は構文内のプレースホルダーです。 ほとんどは、この構文概要の他の場所で定義されています。 定義は再帰的に行うことができます。 次の非終端要素が定義されている、[構文規則](../cpp/lexical-conventions.md)のセクション、 *C++ 言語リファレンス*:

`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`

省略可能な構成要素には添字 <sub>opt</sub> を付けます。 たとえば、次の例では、省略可能な式が中かっこで囲まれています。

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>関連項目

[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)