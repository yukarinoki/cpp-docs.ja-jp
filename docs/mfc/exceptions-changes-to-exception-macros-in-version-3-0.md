---
title: '例外: Version 3.0 での例外処理マクロの変更 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4e6c7744c3d5328985eee24e67ee1eb359fb3c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931019"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>例外処理 : MFC 3.0 での変更点
これは、高度なトピックです。  
  
 Mfc バージョン 3.0 以降、C++ 例外を使用する例外処理マクロを変更されています。 この記事では、これらの変更が既存のコードのマクロを使用する動作に影響する方法を説明します。  
  
 ここでは、次のトピックについて説明します。  
  
-   [例外の種類と、CATCH マクロ](#_core_exception_types_and_the_catch_macro)  
  
-   [例外の再スロー](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> 例外の種類と、CATCH マクロ  
 MFC の以前のバージョンで、**キャッチ**マクロは、例外の種類を判断する MFC の実行時型情報を使用。 例外の型が決定されます、つまり、キャッチ側でします。 C++ の例外を除き、ただし、例外の型は常にスロー サイトでによって決まりますがスローされる例外オブジェクトの種類。 スローされたオブジェクトへのポインターの型がスローされたオブジェクトの種類を異なる位置、まれなケースで互換性が失われます。  
  
 次の例では、MFC バージョン 3.0 と以前のバージョンの間には、この違いの結果を示します。  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 このコードでは動作が異なるバージョン 3.0 コントロールが常に最初に渡すため**キャッチ**例外宣言に一致するとブロックされます。 Throw 式の結果  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 としてスローされる、`CException*`として構成する場合でも、`CCustomException`です。 **キャッチ**マクロで以前使用して MFC バージョン 2.5`CObject::IsKindOf`を実行時に、型をテストします。 式  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 true の場合、最初の catch ブロックが例外をキャッチします。 C++ 例外処理を使用して、さまざまな例外処理マクロを実装する、バージョン 3.0 では、2 番目の catch ブロックと一致する、スローされた`CException`です。  
  
 次のようにコードが共通ではありません。 例外オブジェクトがジェネリック型を受け取る別の関数に渡されるときに通常表示される`CException*`「スロー」処理を行い、最後に、例外がスローされます。  
  
 この問題を回避するには、関数からスロー式を呼び出し元のコードに移動し、例外が生成された時点にコンパイラに認識されている実際の型の例外をスローします。  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> 例外の再スロー  
 Catch ブロックには、それをキャッチした例外ポインターをスローできません。  
  
 たとえば、このコードは以前のバージョンで有効ですがバージョン 3.0 から予期しない結果。  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 使用して**スロー** catch ブロックが発生したポインター`e`外側の catch サイトは無効なポインターを受け取れるように、削除します。 使用して**THROW_LAST**を再スロー`e`です。  
  
 詳細については、次を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
## <a name="see-also"></a>関連項目  
 [例外処理](../mfc/exception-handling-in-mfc.md)

