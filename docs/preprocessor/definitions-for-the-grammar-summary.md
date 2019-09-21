---
title: 文法の概要での定義
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 93cf6ffc5daf53a106c9f15a2289e2b52739d72f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222413"
---
# <a name="definitions-for-the-grammar-summary"></a>文法の概要での定義

終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。

非終端は構文内のプレースホルダーです。 ほとんどは、この構文概要の他の場所で定義されています。 定義は再帰的に行うことができます。 次の非終端要素は、  *C++言語リファレンス*の[構文規則](../cpp/lexical-conventions.md)のセクションで定義されています。

*定数*、*定数式*、*識別子*、*キーワード*、*演算子*、*など*

省略可能な構成要素には添字 <sub>opt</sub> を付けます。 たとえば、次の例では、省略可能な式が中かっこで囲まれています。

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>関連項目

[文法の概要 (CC++/)](../preprocessor/grammar-summary-c-cpp.md)
