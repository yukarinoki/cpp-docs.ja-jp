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
ms.openlocfilehash: 2073729fc5445fc36e3d8a6f52c4f69b079c8b47
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462132"
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp の使用
ときに[setjmp](../c-runtime-library/reference/setjmp.md)と[longjmp](../c-runtime-library/reference/longjmp.md)は非ローカルを実行する方法を提供を一緒に使用**goto**します。 これらは通常、標準呼び出し規約や復帰規約を使用せずに、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。  
  
> [!CAUTION]
>  ただし、ため**setjmp**と**longjmp** C++ オブジェクトのセマンティクスをサポートしていませんし、使用しないことをお勧めするローカル変数の最適化を防ぐことによってパフォーマンスが低下する可能性があります、ため、C++ プログラムにします。 使用することをお勧めします。**お試しください**/**キャッチ**代わりに構築します。  
  
 使用する場合**setjmp**/**longjmp** 、C++ プログラムでも含める\<setjmp.h > または\<setjmpex.h > の間の相互作用を保証するために、関数と C++ 例外処理します。 使用する場合[/EH](../build/reference/eh-exception-handling-model.md)をコンパイルするローカル オブジェクトのデストラクターがスタック アンワインド中に呼び出されます。 使用する場合 **/EHs**コンパイル、および関数の呼び出しを使用する関数の 1 つに[nothrow](../cpp/nothrow-cpp.md)と関数を使用する**nothrow**呼び出し**longjmp**、デストラクター アンワインドが発生しない場合、オプティマイザーによってします。  
  
 移植可能なコード、ときに、非ローカルの**goto**を呼び出す**longjmp**実行すると、フレーム ベースのオブジェクトの適切な破棄が信頼性が高くない可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)