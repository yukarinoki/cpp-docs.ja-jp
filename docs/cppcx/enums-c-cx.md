---
title: 列挙型 (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 725e2b9edb7ba2a84418e900ffb1aafe4c5064af
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593965"
---
# <a name="enums-ccx"></a>列挙型 (C++/CX)
C +/cli CX のサポート、`public enum class`キーワード、標準の C++ に似ている`scoped  enum`します。 `public enum class` キーワードを使用して宣言された列挙子を使用する場合、列挙体識別子を使用して各列挙子値の範囲を指定する必要があります。  
  
### <a name="remarks"></a>Remarks  
 `public enum class` など、アクセス指定子を持たない `public`は、標準 C++ の [スコープ列挙体](../cpp/enumerations-cpp.md)として扱われます。  
  
 A`public enum class`または`public enum struct`宣言は、Windows ランタイム自体は、int32、またはフラグ列挙型の uint32 型であることが必要ですが、基になる型の任意の整数型を持つことができます。 次の構文は、 `public enum class` または `public enum struct`の各部分を説明します。  
  
 この例は、パブリック列挙型クラスを定義する方法を示しています。  
  
 [!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]  
  
 この次の例では、それを利用する方法を示しています。  
  
 [!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]  
  
### <a name="examples"></a>使用例  
 次の例は、列挙型を宣言する方法を示します。  
  
 [!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]  
  
 次の例は、同等の数値にキャストし、比較を実行する方法を示しています。 列挙子 `One` の使用範囲は `Enum1` 列挙体識別子により指定され、列挙子 `First` の範囲は `Enum2`によって指定されることに注意してください。  
  
 [!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]  
  
## <a name="see-also"></a>関連項目  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)