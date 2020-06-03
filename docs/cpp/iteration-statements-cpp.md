---
title: 繰り返しステートメント (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
ms.openlocfilehash: e8f064fd19e69de2819673f48a7f14e26d60b87e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178258"
---
# <a name="iteration-statements-c"></a>繰り返しステートメント (C++)

繰り返しステートメントにより、ループ終了条件に応じて、ステートメント (または複合ステートメント) が複数回実行されます。 これらのステートメントが複合ステートメントである場合、 [break](../cpp/break-statement-cpp.md)ステートメントまたは[continue](../cpp/continue-statement-cpp.md)ステートメントのいずれかが検出されている場合を除き、ステートメントは順番に実行されます。

C++には、 [while](../cpp/while-statement-cpp.md)、 [do](../cpp/do-while-statement-cpp.md)、 [for](../cpp/for-statement-cpp.md)、[範囲ベースのの](../cpp/range-based-for-statement-cpp.md)4 つの反復ステートメントが用意されています。 これらの各は、終了式が 0 (false) に評価されるか、またはループの終了が**break**ステートメントで強制されるまで反復処理されます。 次の表は、これらのステートメントと操作をまとめたものです。それぞれについては以降のセクションで詳しく説明します。

### <a name="iteration-statements"></a>繰り返しステートメント

|ステートメント|評価のタイミング|初期化|Increment|
|---------------|------------------|--------------------|---------------|
|**while**|ループの先頭|いいえ|いいえ|
|**do**|ループの最後|いいえ|いいえ|
|**for**|ループの先頭|はい|はい|
|**範囲ベースの**|ループの先頭|はい|はい|

繰り返しステートメントのステートメント部分は宣言にできません。 ただし、宣言を含む複合ステートメントにすることができます。

## <a name="see-also"></a>参照

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
