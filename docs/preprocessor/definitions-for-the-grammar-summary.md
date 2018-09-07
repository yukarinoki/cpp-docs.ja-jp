---
title: 文法の概要の定義 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c11f2f839ef806d74eae65c9fc8fe3a71cd2e9c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760818"
---
# <a name="definitions-for-the-grammar-summary"></a>文法の概要での定義

終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。

非終端は構文内のプレースホルダーです。 ほとんどは、この構文概要の他の場所で定義されています。 定義は再帰的に行うことができます。 次の非終端要素が定義されている、[構文規則](../cpp/lexical-conventions.md)のセクション、 *C++ 言語リファレンス*:

`constant`、*定数式*、*識別子*、*キーワード*、 `operator`、 `punctuator`

オプションのコンポーネントが示される、添字で<sub>opt</sub>します。 たとえば、次の例では、省略可能な式が中かっこで囲まれています。

**{** *式*<sub>opt</sub> **}**

## <a name="see-also"></a>関連項目

[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)