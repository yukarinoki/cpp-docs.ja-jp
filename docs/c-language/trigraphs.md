---
title: トライグラフ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ??) trigraph
- ??- trigraph
- question mark, in trigraphs
- ??= trigraph
- ?? trigraph
- ??< trigraph
- ??/ trigraph
- trigraphs
- '? symbol, trigraph'
- ??> trigraph
- ??! trigraph
- ??' trigraph
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb65bf8cf2f9585ff12ba0a098d9ca441310933f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101939"
---
# <a name="trigraphs"></a>トライグラフ

C ソース プログラムのソース文字セットは 7 ビットの ASCII 文字セット内に含まれますが、ISO 646-1983 Invariant Code Set のスーパーセットです。 トライグラフ シーケンスでは、ISO (国際標準化機構) の Invariant Code Set のみを使用して C プログラムを記述できます。 トライグラフは、2 つの連続する疑問符で始まる 3 文字のシーケンスで、これがコンパイラにより対応する区切り文字に置き換えられます。 トライグラフは、一部の区切り文字に対応する適切なグラフィック表示がない文字セットを含む C ソース ファイルで使用できます。

C++ 17 では、言語からトライグラフが削除されます。 実装ではトライグラフを物理ソース ファイルから*基本ソース文字セット*への実装定義マッピングの一部として引き続きサポートできるものの、標準ではそれをしないよう実装に対して勧めています。 C++14 までトライグラフは C と同様にサポートされていました。

既定で無効になっていますが、Visual C++ はトライグラフの置換をサポートし続けます。 トライグラフの置換を有効にする方法の詳細については、「[/Zc:trigraphs (トライグラフの置換)](../build/reference/zc-trigraphs-trigraphs-substitution.md)」をご覧ください。

次の表は、9 つのトライグラフ シーケンスを示しています。 最初の列の区切り文字がソース ファイルに出現すると、すべて 2 番目の列の対応する文字に置き換えられます。

### <a name="trigraph-sequences"></a>トライグラフ シーケンス

|トライグラフ|区切り文字|
|--------------|---------------------------|
|??=|#|
|??(|[|
|??/|\|
|??)|]|
|??'|^|
|??\<|{|
|??!|&#124;|
|??>|}|
|??-|~|

トライグラフは、常に 1 つのソース文字として処理されます。 トライグラフの変換は、文字列リテラルと文字定数のエスケープ文字を認識する前の、最初の[変換フェーズ](../preprocessor/phases-of-translation.md)で実行されます。 認識されるのは、上の表に示した 9 つのトライグラフだけです。 他の文字シーケンスは、変換されません。

文字エスケープ シーケンス **\\?** を使用すると、トライグラフに似た文字シーケンスが誤ってトライグラフとして解釈されないようにできます。 (エスケープ シーケンスについては、「[エスケープ シーケンス](../c-language/escape-sequences.md)」を参照してください。)たとえば、`What??!` ステートメントを使用して文字列 `printf` を印刷しようとして、次のようにしたとします。

```
printf( "What??!\n" );
```

出力される文字列は `What|` です。これは、`??!` がトライグラフ シーケンスであり、`|` 文字に置き換えられるためです。 この文字列を正しく印刷するには、次のようにステートメントを記述します。

```
printf( "What?\?!\n" );
```

この `printf` ステートメントでは、2 番目の疑問符の前に円記号のエスケープ文字があることで、`??!` が誤ってトライグラフとして解釈されないようになります。

## <a name="see-also"></a>参照

[/Zc:trigraphs (トライグラフの置換)](../build/reference/zc-trigraphs-trigraphs-substitution.md)<br/>
[C の識別子](../c-language/c-identifiers.md)