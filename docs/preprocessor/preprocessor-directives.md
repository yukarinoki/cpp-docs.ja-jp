---
title: プリプロセッサ ディレクティブ
ms.date: 06/28/2018
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: 9481e977f2afb3de27a74278893a217fde48044b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179972"
---
# <a name="preprocessor-directives"></a>プリプロセッサ ディレクティブ

プリプロセッサ ディレクティブなど`#define`と`#ifdef`、通常を使用してソース プログラムを簡単に変更し、異なる実行環境でコンパイルを容易にします。 ソース ファイルのディレクティブはプリプロセッサに特定のアクションを実行するよう通知します。 たとえば、プリプロセッサは、テキストのトークンを置き換えたり、ソース ファイルに他のファイルの内容を挿入したり、テキストのセクションの削除によりファイルの一部のコンパイルを中止したりできます。 プリプロセッサ行は、マクロの展開の前に認識され、実行されます。 したがって、マクロがプリプロセッサ コマンドのように見えるコマンドに展開されても、そのコマンドはプリプロセッサによって認識されません。

プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。 プリプロセッサ ステートメントで使用される文字セットは、実行文字セットと同じです。 プリプロセッサは、負の文字値も認識します。

プリプロセッサは次のディレクティブを認識します。

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

シャープ記号 (**#**) する必要があります。 ディレクティブを含む行で最初の非空白文字を指定、番号記号とディレクティブの最初の文字間の空白文字を表示できます。 一部のディレクティブには、引数または値が含まれます。 単一行コメントの区切り記号の前が必要 (引数またはディレクティブの一部である値) を除く、ディレクティブに続くテキスト (**//**) コメントの区切り記号で囲まれた、または ( __/\*\*/__). プリプロセッサ ディレクティブを含む行を継続するには円記号では、行末マーカーの直前に (**\\**)。

プリプロセッサ ディレクティブはソース ファイル内の任意の場所で使用できますが、ソース ファイルの残りの部分だけに適用されます。

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)<br/>
[定義済みマクロ](../preprocessor/predefined-macros.md)<br/>
[C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)
