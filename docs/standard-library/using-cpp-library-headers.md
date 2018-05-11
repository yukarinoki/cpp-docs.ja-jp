---
title: C++ ライブラリ ヘッダーの使用 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- headers, naming in C++ include directive
- standard header in C++
- headers
- INCLUDE directive
- headers, C++ Standard Library
- library headers
- C++ Standard Library, headers
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30d31f30971184356374b3991fedda474ca27465
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="using-c-library-headers"></a>C++ ライブラリ ヘッダーの使用

標準ヘッダーの内容は、include ディレクティブで指定することによって含めます。

```cpp
#include <iostream>// include I/O facilities
```

標準ヘッダーは、複数回、任意の順序で含めることができます。また、2 つ以上の標準ヘッダーで、同じマクロや同じ型を定義できます。 標準ヘッダーは宣言内に含めないでください。 標準ヘッダーを含める前に、キーワードと同じ名前のマクロを定義しないでください。

C++ ライブラリ ヘッダーには、それが必要とする型の定義に必要な、他のすべての C++ ライブラリ ヘッダーが含まれています。 (ただし、実際の依存関係について誤解が生じないように、翻訳単位で必要となるすべての C++ ライブラリ ヘッダーを常に明示的に含めてください。)標準 C ヘッダーには別の標準ヘッダーを含めないでください。 標準ヘッダーでは、このドキュメントで説明されているエンティティのみを宣言または定義します。

ライブラリ内のすべての関数は、標準ヘッダーで宣言されます。 標準 C とは異なり、標準ヘッダーには、関数の宣言をマスクして同じ効果を得るために、関数と同じ名前のマスキング マクロを指定することはありません。 マスキング マクロの詳細については、「[C++ ライブラリの規則](../standard-library/cpp-library-conventions.md)」を参照してください。

C++ ライブラリ ヘッダーの、`operator delete` と `operator new` を除くすべての名前は、`std` 名前空間か、`std` 名前空間内に入れ子になった名前空間で定義されます。 たとえば、名前 `cin` を `std::cin` として参照します。 ただし、マクロ名は名前空間修飾子ではないため、`__STD_COMPLEX` は常に名前空間修飾子なしで記述します。

C++ ライブラリ ヘッダーのように、翻訳環境の中には、名前ごとに個別の `using` 宣言を使用して、`std` 名前空間で宣言された外部名もグローバル名前空間に含めるものがあります。 それ以外の場合、ヘッダーでは、現在の名前空間にライブラリ名を含めることは*ありません*。

C++ 標準によって、C 標準ヘッダーで名前空間 `std` のすべての外部名を宣言することが要求されるため、それぞれの名前に `using` 宣言を付けて、これらをグローバル名前空間に含めます。 ただし、翻訳環境によっては、C 標準ヘッダーに名前空間宣言が含まれず、グローバル名前空間で直接すべての名前を宣言する場合があります。 このため、次の 2 つの規則に従うことが、名前空間を処理する最もポータブルな方法となります。

- 従来 \<stdlib.h> で宣言されていた外部名を、名前空間 `std` で確実に宣言するために、たとえば \<cstdlib> を含めます。 この名前が、グローバル名前空間でも宣言されている可能性があることを認識してください。

- \<stdlib.h> で宣言されている外部名を、グローバル名前空間で確実に宣言するために、\<stdlib.h> を含めます。 この名前が、名前空間 `std` でも宣言されている可能性があることを認識してください。

したがって、異常終了が発生するように `std::abort` を呼び出す場合は、\<cstdlib> を含める必要があります。 `abort` を呼び出す場合は、\<stdlib.h> を含める必要があります。

別の方法として、次の宣言を記述できます。

```cpp
using namespace std;
```

これにより、すべてのライブラリ名が現在の名前空間に含められます。 この宣言をすべての include ディレクティブの直後に記述すると、それらの名前がグローバル名前空間に含められます。 その後、翻訳単位の残りの部分で名前空間の考慮事項を無視できます。 また、異なる翻訳環境間での多くの違いを回避することもできます。

他の方法で特に指定しない限り、プログラム内で、`std` 名前空間、および `std` 名前空間内に入れ子になった名前空間で名前を定義することはできません。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
