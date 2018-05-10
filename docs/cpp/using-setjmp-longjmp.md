---
title: Setjmp longjmp の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee79d5b81e968e89e8072fb545c86f33be9bcce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp の使用
ときに[setjmp](../c-runtime-library/reference/setjmp.md)と[longjmp](../c-runtime-library/reference/longjmp.md)は一緒に使用すると、ローカル以外の実行方法を提供`goto`です。 これらは通常、標準呼び出し規約や復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
> [!CAUTION]
>  ただし、`setjmp` と `longjmp` は C++ オブジェクトのセマンティクスをサポートせず、ローカル変数の最適化を妨げることによってパフォーマンスを低下させる可能性があるため、C++ プログラムでは使用しないことをお勧めします。 使用することをお勧め`try` / `catch`代わりに構築します。  
  
 利用を決めた場合`setjmp` / `longjmp` 、C++ プログラムでも含める\<setjmp.h > または\<setjmpex.h > 関数と C++ 例外処理の間の相互作用が正しくにします。 使用する場合[/EH](../build/reference/eh-exception-handling-model.md)をコンパイルするローカル オブジェクトのデストラクターがスタック アンワインド中に呼び出されます。 使用する場合 **/EHs**コンパイル、および、関数呼び出しを使用する関数の 1 つに[nothrow](../cpp/nothrow-cpp.md)と関数を使用する`nothrow`呼び出し`longjmp`、デストラクター アンワインドが発生しない場合、オプティマイザーに依存します。  
  
 移植性のあるコードで、`goto` を呼び出す非ローカルの `longjmp` が実行される場合、フレーム ベースのオブジェクトの適切な破棄が行われない可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)