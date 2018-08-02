---
title: try-finally ステートメント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
dev_langs:
- C++
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 043c11a6255e3b80fde176f1b2525e8285bbff12
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464861"
---
# <a name="try-finally-statement"></a>try-finally ステートメント
**Microsoft 固有の仕様**  
  
 次の構文について説明します、 **、try-finally**ステートメント。  
  
```cpp 
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## <a name="grammar"></a>文法  
 *try-finally-statement*:  
 **_ _try** *複合ステートメント*  
  
 **_ _finally** *複合ステートメント*  
  
 **、Try-finally**ステートメントは C および C++ 言語への Microsoft 拡張コードのブロックの実行が中断されたときにクリーンアップ コードの実行を保証するためにターゲット アプリケーションの機能です。 クリーンアップは、メモリを解放する、ファイルを閉じる、ファイル ハンドルを解放するなどのタスクで構成されます。 **、Try-finally**ステートメントは、チェックが行われる場所を引き起こす可能性のあるエラーの途中の複数の場所のルーチンは、ルーチンから返すに特に便利です。  
  
 関連する情報とコード サンプルでは、次を参照してください。[を再試行してください-ステートメントを除く](../cpp/try-except-statement.md)します。 詳細については、構造化例外処理を一般には、次を参照してください。[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)します。 マネージ アプリケーションでの例外処理の詳細については、次を参照してください。 [/clr での例外処理](../windows/exception-handling-cpp-component-extensions.md)します。  
  
> [!NOTE]
>  構造化例外処理では、C と C++ のソース ファイルの両方で Win32 を使用します。 ただし、特に C++ 用にデザインされたものではありません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理は、任意の型の例外を処理できるという点で、より柔軟です。 C++ プログラムは、お勧め、C++ 例外処理機構を使用すること ([try、catch、および throw](../cpp/try-throw-and-catch-statements-cpp.md)ステートメント)。  
  
 後の複合ステートメント、 **_ _try**句は、保護されたセクションです。 後の複合ステートメント、 **_ _finally**句は、終了ハンドラー。 ハンドラーは、保護されたセクションが例外によって終了 (異常終了) したか、標準的なフォール スルー (正常終了) で終了したかにかかわらず、保護されたセクションが終了したときに実行する一連の操作を指定します。  
  
 コントロールに達すると、 **_ _try**単純な順次実行 (フォール スルー) によってステートメント。 コントロールに入ったとき、 **_ _try**、その関連付けられたハンドラーがアクティブになります。 制御のフローが try ブロックの終わりに到達すると、次のように実行は処理されます。  
  
1.  終了ハンドラーが呼び出されます。  
  
2.  後に実行が続行、終了ハンドラーが完了したら、 **_ _finally**ステートメント。 セクションが終了を保護する方法にかかわらず (経由など、 **goto**本体外のまたは**返す**ステートメント)、終了ハンドラーが実行される*する前に*制御フローが保護されたセクション外へ移動します。  
  
     A **_ _finally**ステートメントは、適切な例外ハンドラーの検索をブロックしません。  
  
 例外が発生した場合、 **_ _try**ブロック、例外のハンドラーを見つける必要があります、オペレーティング システムまたはプログラムは失敗します。 ハンドラーが見つかった場合、すべて **_ _finally**ブロックが実行され、ハンドラーの実行が再開します。  
  
 たとえば、次の図に示すように、一連の関数呼び出しで、関数 A を関数 D にリンクするとします。 各関数には、1 つの終了ハンドラーがあります。 関数 D で例外が発生し、A で処理されると、スタックがアンワインドされるときに、終了ハンドラーは D、C、B の順に呼び出されます。  
  
 ![終了の順序&#45;ハンドラーの実行](../cpp/media/vc38cx1.gif "vc38CX1")  
終了順序 - ハンドラーの実行  
  
> [!NOTE]
>  Try-finally の動作の使用をサポートする他の言語とは異なります**最後に**、c# など。  1 つ **_ _try**の両方ではなくが、必要があります **_ _finally**と **_ _except**します。  両方を一緒に使用する場合は、外側の try-except ステートメントで内側の try-finally ステートメントを囲む必要があります。  各ブロックがいつ実行されるかを指定する規則も異なります。  
  
## <a name="the-leave-keyword"></a>__leave キーワード  
 **_ _Leave**キーワードの保護されたセクション内でのみ有効ですが、 **、try-finally**ステートメント、およびその効果、保護されたセクションの末尾に移動することです。 実行は、終了ハンドラーの最初のステートメントに移って続行されます。  
  
 A **goto**ステートメントは、保護されたセクションからも移動できますが、スタック アンワインドを呼び出すため、パフォーマンスが低下します。 **_ _Leave**スタック アンワインドが発生しないために、ステートメントが効率的です。  
  
## <a name="abnormal-termination"></a>異常終了  
 終了、 **、try-finally**ステートメントを使用して、 [longjmp](../c-runtime-library/reference/longjmp.md)ランタイム関数が異常終了と見なされます。 移動することはできません、 **_ _try**ステートメントがジャンプして出る 1 つ。 すべて **_ _finally**出発点間アクティブであるステートメント (の正常終了、 **_ _try**ブロック) と変換先 (、 **_ _except**ブロックします。例外のハンドル) 実行する必要があります。 これは、ローカル アンワインドと呼ばれます。  
  
 場合、**お試しください**ブロックからのジャンプを含む、何らかの理由でブロックが終了途中で、システムに関連付けられている実行**最後に**スタックをアンワインドするプロセスの一部としてブロックします。 このような場合、 [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265)関数が返される**true**内から呼び出された場合、**最後に**ブロック以外を返しますそれ以外の場合、 **false**.  
  
 実行中にプロセスが中止された場合、終了ハンドラーは呼び出されません、 **、try-finally**ステートメント。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [終了ハンドラーの記述](../cpp/writing-a-termination-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [終了ハンドラーの構文](http://msdn.microsoft.com/library/windows/desktop/ms681393)