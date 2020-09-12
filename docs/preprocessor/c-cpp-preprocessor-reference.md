---
title: C/C++ のプリプロセッサ リファレンス
description: Visual Studio での Microsoft C/c + + コンパイラプリプロセッサのリファレンスです。
ms.date: 09/10/2020
helpviewer_keywords:
- preprocessor
- preprocessor, reference overview
ms.assetid: e4a52843-7016-4f6d-8b40-cb1ace18f805
ms.openlocfilehash: e53f7270a71e5e7c3f456be7d55d49eaf352aecb
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040744"
---
# <a name="cc-preprocessor-reference"></a>C/C++ のプリプロセッサ リファレンス

『 *C/c + + プリプロセッサリファレンス* 』では、Microsoft c/c + + で実装されているプリプロセッサについて説明しています。 プリプロセッサは C および C++ ファイルをコンパイラに渡す前の準備的な処理を実行します。 プリプロセッサを使用して、コードの条件付きコンパイル、ファイルの挿入、コンパイル時のエラー メッセージの指定、コード セクションへのコンピューター固有の規則の適用を行うことができます。

Visual Studio 2019 では、 [/実験的: プリプロセッサ](../build/reference/experimental-preprocessor.md) コンパイラオプションを使用すると、プリプロセッサの新しい実装が有効になります。 新しい実装はまだ進行中であるため、実験的と見なされます。 最終的には、C99、C11、および C++ 20 に準拠していることを意図しています。 詳細については、「 [MSVC new プリプロセッサの概要](preprocessor-experimental-overview.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[プリプロセッサ](preprocessor.md)\
従来のプリプロセッサと新しい準拠するものの概要について説明します。

[プリプロセッサディレクティブ](../preprocessor/preprocessor-directives.md)\
さまざまな実行環境でのソース プログラムの変更やコンパイルを容易にするために通常使用される、ディレクティブについて説明します。

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)\
`#define` ディレクティブのコンテキストで使用される、4 つのプリプロセッサ固有の演算子について説明します。

[定義済みマクロ](../preprocessor/predefined-macros.md)\
C および C++ 標準および Microsoft C++ によって指定された定義済みマクロについて説明します。

[プラ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
各コンパイラが C 言語および C++ 言語の全体的な互換性を維持しながら、コンピューター固有の機能およびオペレーティング システム固有の機能を提供するために使用される、プラグマについて説明します。

## <a name="related-sections"></a>関連項目

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)\
C++ 言語の Microsoft 実装に関するリファレンス ドキュメントを紹介します。

[C 言語リファレンス](../c-language/c-language-reference.md)\
C 言語の Microsoft 実装に関するリファレンス ドキュメントを紹介します。

[C/c + + ビルドリファレンス](../build/reference/c-cpp-building-reference.md)\
コンパイラとリンカーのオプション関するトピックへのリンクを示します。

[Visual Studio プロジェクト-C++](../build/creating-and-managing-visual-cpp-projects.md)\
プロジェクト システムが C++ プロジェクトのファイルを見つけるために検索するディレクトリを指定できる、Visual Studio のユーザー インターフェイスについて説明します。
