---
title: Setjmp-longjmp の使用 |Microsoft Docs
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
ms.openlocfilehash: f68cd13304e73282735ad1227510b289b19caed8
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939768"
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp の使用
ときに[setjmp](../c-runtime-library/reference/setjmp.md)と[longjmp](../c-runtime-library/reference/longjmp.md)は非ローカルを実行する方法を提供を一緒に使用**goto**します。 これらは通常、標準呼び出し規約や復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
> [!CAUTION]
>  ただし、`setjmp` と `longjmp` は C++ オブジェクトのセマンティクスをサポートせず、ローカル変数の最適化を妨げることによってパフォーマンスを低下させる可能性があるため、C++ プログラムでは使用しないことをお勧めします。 使用することをお勧めします。**お試しください**/**キャッチ**代わりに構築します。  
  
 使用する場合`setjmp` / `longjmp` 、C++ プログラムでも含める\<setjmp.h > または\<setjmpex.h > 関数と C++ 例外処理の間の相互作用します。 使用する場合[/EH](../build/reference/eh-exception-handling-model.md)をコンパイルするローカル オブジェクトのデストラクターがスタック アンワインド中に呼び出されます。 使用する場合 **/EHs**コンパイル、および関数の呼び出しを使用する関数の 1 つに[nothrow](../cpp/nothrow-cpp.md)と関数を使用する**nothrow**呼び出し`longjmp`、オプティマイザーによって、このデストラクター アンワインドが発生する可能性がありますされません。  
  
 移植可能なコード、ときに、非ローカルの**goto**を呼び出す`longjmp`実行すると、フレーム ベースのオブジェクトの適切な破棄が信頼性が高くない可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)