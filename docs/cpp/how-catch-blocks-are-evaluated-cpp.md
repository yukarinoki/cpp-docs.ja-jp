---
title: Catch ブロックの評価方法 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f073f82114c2d58b6d4d94bfeb35048b9e676c45
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405536"
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch ブロックの評価方法 (C++)
C++ では任意の型の例外をスローすることができますが、一般に std::exception から派生した型をスローすることが推奨されます。 C++ 例外をキャッチできる、**キャッチ**または任意の種類の例外をキャッチできるハンドラーによってスローされた例外として、同じ型を指定するハンドラー。  
  
 スローされる例外の型がクラスである場合、クラスは基底クラスも持つため、その例外は、例外の型の基底クラスを受け入れるハンドラー、および例外の型の基底クラスへの参照を受け入れるハンドラーでキャッチできます。 例外が参照によってキャッチされた場合、それは実際にスローされた例外オブジェクトにバインドされることに注意してください。それ以外の場合は、コピーになります (関数の引数とほぼ同じ)。  
  
 例外がスローされたときに、次の種類のによってキャッチできます**キャッチ**ハンドラー。  
  
-   任意の型を受け取ることができるハンドラー (省略記号構文を使用)。  
  
-   例外オブジェクトと同じ型を受け入れるハンドラーこれは、コピーであるため**const**と**揮発性**修飾子は無視されます。  
  
-   例外オブジェクトと同じ型への参照を受け入れるハンドラー。  
  
-   参照を受け入れるハンドラー、 **const**または**揮発性**例外オブジェクトと同じ型の形式。  
  
-   例外オブジェクトと同じ型の基本クラスを受け入れるハンドラーこれは、コピー後**const**と**揮発性**修飾子は無視されます。 **キャッチ**基底クラスのハンドラーの前にする必要があります、**キャッチ**派生クラスのハンドラー。  
  
-   例外オブジェクトと同じ型の基底クラスへの参照を受け取るハンドラー。  
  
-   参照を受け入れるハンドラー、 **const**または**揮発性**例外オブジェクトと同じ型の基底クラスの形式。  
  
-   スローされたポインター オブジェクトが標準的なポインター変換規則によって変換できるポインターを受け取るハンドラー。  
  
 順序**キャッチ**ハンドラーの表示は、重要ではためのハンドラーを特定**お試しください**ブロックは、それらの外観の順序でチェックされます。 たとえば、派生クラスのハンドラーの前に基底クラスのハンドラーを配置するとエラーになります。 一致すた後**キャッチ**ハンドラーが見つかると、後続のハンドラーはチェックされません。 その結果、省略記号**キャッチ**ハンドラーは、最後のハンドラーである必要があります、**お試しください**ブロックします。 例えば:  
  
```cpp 
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 この例では、省略記号で**キャッチ**ハンドラーが唯一のハンドラーが解析されます。  
  
## <a name="see-also"></a>関連項目  
 [C++ 例外処理](../cpp/cpp-exception-handling.md)