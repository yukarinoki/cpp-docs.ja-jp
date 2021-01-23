---
description: pragmaMicrosoft C/c + + での execution_character_set ディレクティブの詳細については、こちらを参照してください。
title: execution_character_set pragma
ms.date: 01/22/2021
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma, execution_character_set
- execution_character_set pragma
no-loc:
- pragma
ms.openlocfilehash: cc768aa0d35fffc9c387b31870adf47f35073f35
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712857"
---
# <a name="execution_character_set-no-locpragma"></a>`execution_character_set` pragma

文字列リテラルおよび文字リテラルに使用される実行文字セットを指定します。 このディレクティブは、プレフィックスでマークされているリテラルには必要ありません `u8` 。

## <a name="syntax"></a>構文

> **`#pragma execution_character_set(`** "*ターゲット*" **`)`**

### <a name="parameters"></a>パラメーター

*接続*\
ターゲットの実行文字セットを指定します。 現在サポートされているターゲット実行セットは "utf-8" だけです。

## <a name="remarks"></a>解説

このコンパイラディレクティブは、Visual Studio 2015 Update 2 以降では廃止されました。 **`/execution-charset:utf-8`** またはのコンパイラオプションは、 **`/utf-8`** `u8` 拡張文字を含むナロー文字とリテラル文字列のプレフィックスを使用することをお勧めします。 プレフィックスの詳細については `u8` 、「 [文字列リテラルと文字リテラル](../cpp/string-and-character-literals-cpp.md)」を参照してください。 コンパイラオプションの詳細については、「 [ `/execution-charset` (実行文字セットの設定)](../build/reference/execution-charset-set-execution-character-set.md) 」および「 [ `/utf-8` (ソースと実行可能文字セットを utf-8 に設定する)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)」を参照してください。

ディレクティブは、 `#pragma execution_character_set("utf-8")` ソースコード内のナロー文字とナロー文字列リテラルを実行可能ファイルの utf-8 としてエンコードするようコンパイラに指示します。 この出力エンコーディングは、使用されるソースファイルのエンコードに依存しません。

既定では、コンパイラは、現在のコードページを実行文字セットとして使用して、ナロー文字とナロー文字列をエンコードします。 これは、現在のコードページの範囲外の Unicode または DBCS 文字が出力の既定の置換文字に変換されることを意味します。 Unicode と DBCS の文字は下位バイトに切り捨てられますが、これは意図したとおりにはほとんどありません。 プレフィックスを使用して、ソースファイル内のリテラルに UTF-8 エンコードを指定でき `u8` ます。 コンパイラは、これらの UTF-8 でエンコードされた文字列を出力に変更せずに渡します。 U8 を使用してプレフィックスが付いたナロー文字リテラルは、バイトに収める必要があります。または、出力時に切り捨てられます。

既定では、Visual Studio は、出力のソースコードを解釈するために使用されるソース文字セットとして、現在のコードページを使用します。 ファイルが読み込まれると、Visual Studio は、ファイルコードページが設定されていない場合、またはファイルの先頭でバイト順マーク (BOM) または UTF-16 文字が検出されなかった場合に、現在のコードページに従って解釈します。 一部のバージョンの Windows では、UTF-8 を現在のコードページとして設定することはできません。 自動検出で、UTF-8 としてエンコードされたソースファイルがこれらのバージョンの BOM なしで検出されると、Visual Studio は現在のコードページを使用してエンコードされているものと見なします。 ソースファイル内の指定したコードページまたは自動的に検出されたコードページの範囲外にある文字は、コンパイラの警告とエラーを引き起こす可能性があります。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)\
[`/execution-charset` (実行文字セットの設定)](../build/reference/execution-charset-set-execution-character-set.md)\
[`/utf-8` (ソースと実行可能文字セットを UTF-8 に設定します)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
