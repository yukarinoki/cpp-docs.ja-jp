---
title: プリプロセッサ ディレクティブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b73f6ce579f94d38621820a63888dc0aa5a75863
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849887"
---
# <a name="preprocessor-directives"></a>プリプロセッサ ディレクティブ
プリプロセッサ ディレクティブなど`#define`と **#ifdef**、ソース プログラムを簡単に変更し、異なる実行環境でコンパイルを容易に用いられます。 ソース ファイルのディレクティブはプリプロセッサに特定のアクションを実行するよう通知します。 たとえば、プリプロセッサは、テキストのトークンを置き換えたり、ソース ファイルに他のファイルの内容を挿入したり、テキストのセクションの削除によりファイルの一部のコンパイルを中止したりできます。 プリプロセッサ行は、マクロの展開の前に認識され、実行されます。 したがって、マクロがプリプロセッサ コマンドのように見えるコマンドに展開されても、そのコマンドはプリプロセッサによって認識されません。  
  
 プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。 プリプロセッサ ステートメントで使用した文字セットと同じ、[実行文字セット](http://msdn.microsoft.com/en-us/a7901c61-524d-47c6-beb6-d9dacc2e72ed)です。 プリプロセッサは、負の文字値も認識します。  
  
 プリプロセッサは次のディレクティブを認識します。  
  
|||||  
|-|-|-|-|  
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|  
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 シャープ記号 (**#**) 必要があります、ディレクティブを含む行で最初の非空白文字にするシャープ記号とディレクティブの最初の文字間の空白文字に表示できます。 一部のディレクティブには、引数または値が含まれます。 (引数または値は、ディレクティブの一部である) を除くディレクティブに続くテキストの前に、単一行コメント デリミター (**//**) またはコメントの区切り記号で囲む ( **/\* \*/**). プリプロセッサ ディレクティブを含む行を継続するには、円記号での行末マーカーの直前に (**\\**)。  
  
 プリプロセッサ ディレクティブはソース ファイル内の任意の場所で使用できますが、ソース ファイルの残りの部分だけに適用されます。  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)   
 [定義済みマクロ](../preprocessor/predefined-macros.md)   
 [C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)