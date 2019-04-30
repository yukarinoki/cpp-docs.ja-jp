---
title: execution_character_set
ms.date: 10/18/2018
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: bd31e8e91a1bcbfa6ace9b47fa2b13dd945adb20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389581"
---
# <a name="executioncharacterset"></a>execution_character_set

文字列と文字リテラルに使用する実行文字セットを指定します。 U8 プレフィックスの付いたリテラルでは、このディレクティブは必要ありません。

## <a name="syntax"></a>構文

```
#pragma execution_character_set("target")
```

### <a name="parameters"></a>パラメーター

*target*<br/>
ターゲットの実行文字セットを指定します。 現在サポートされている設定のみのターゲットの実行は"utf-8"です。

## <a name="remarks"></a>Remarks

このコンパイラ ディレクティブは、Visual Studio 2015 Update 2 以降廃止されています。 使用することをお勧め、`/execution-charset:utf-8`または`/utf-8`コンパイラ オプションを使用してと共に、`u8`拡張文字が含まれているナロー文字と文字列リテラルでのプレフィックス。 詳細については、`u8`プレフィックスを参照してください[String and Character Literals](../cpp/string-and-character-literals-cpp.md)します。 コンパイラ オプションの詳細については、次を参照してください。 [(実行文字セット)/execution-charset](../build/reference/execution-charset-set-execution-character-set.md)と[/utf-8 (ソースの設定と実行可能ファイルの文字セットを utf-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)します。

`#pragma execution_character_set("utf-8")`ディレクティブを指定すると、実行可能ファイル、ナロー文字と、ソース コード内のナロー文字列リテラルを utf-8 としてエンコードします。 この出力エンコードは、使用されるソース ファイルのエンコーディング関係ありません。

既定では、コンパイラは、現在のコード ページを使用して、実行文字セットとして、ナロー文字とナロー文字列をエンコードします。 つまり、リテラルには、現在のコード ページの範囲外にある Unicode または DBCS 文字は、出力の既定の置換文字に変換されます。 Unicode と DBCS 文字は、下位バイトに切り捨てられます。 これは、ほぼ間違いなく望ましくないです。 Utf-8 を使用してソース ファイル内のリテラルのエンコードを指定できます、`u8`プレフィックス。 コンパイラは、変更されずに出力に、これらの utf-8 でエンコードされた文字列を渡します。 による u8 プレフィックス付きナロー文字リテラルが 1 つのバイトに収まる必要があるか、出力時に切り捨てられる。

既定では、Visual Studio は、出力のソース コードを解釈するために使用するソース文字セットとして現在のコード ページを使用します。 ファイルが読み取られると、Visual Studio の解釈が現在のコード ページに従ってファイルのコード ページが設定されていない場合、またはファイルの先頭にバイト オーダー マーク (BOM) または utf-16 文字が検出された場合を除き、します。 自動検出は、BOM なしの utf-8 としてエンコードされたソース ファイルを検出すると、として、現在のコード ページ utf-8 を設定することはできません、ため、Visual Studio では、現在のコード ページを使用してエンコードされている前提としています。 範囲指定された、または自動的に検出されたコード ページ コンパイラの警告とエラーが発生することができます、ソース ファイル内の文字。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと\_\_プラグマ キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/execution-charset (実行文字セット)](../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (ソースと実行可能ファイルの文字セットを UTF-8 に設定する)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)