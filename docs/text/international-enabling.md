---
description: '詳細情報: 国際化の有効化'
title: 国際化対応について
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: 15db7e27b65f4225917945820c936e572fc5da94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207268"
---
# <a name="international-enabling"></a>国際化対応について

従来の C および C++ コードのほとんどは、国際対応アプリケーションではうまくいかない文字や文字列の操作について想定しています。 MFC とランタイムライブラリはどちらも Unicode または MBCS をサポートしていますが、実行できる操作はまだあります。 このセクションでは、Visual C++ の "国際化対応" の意味について説明します。

- MFC 関数のパラメーターリストと戻り値の型では、ポータブルデータ型によって Unicode と MBCS の両方が有効になります。 これらの型は、ビルドがシンボル `_UNICODE` またはシンボル (DBCS を意味します) を定義しているかどうかに応じて、適切な方法で条件付きで定義され `_MBCS` ます。 ビルドで定義されている2つのシンボルに応じて、MFC ライブラリのさまざまなバリアントがアプリケーションと自動的にリンクされます。

- クラスライブラリコードは、ポータブルランタイム関数やその他の方法を使用して、正しい Unicode または MBCS の動作を保証します。

- それでも、コード内の特定の種類の国際化タスクを処理する必要があります。

  - どちらの環境でも MFC を移植できるようにする、同じ移植可能なランタイム関数を使用します。

  - マクロを使用して、リテラル文字列と文字をいずれかの環境で移植できるようにし `_T` ます。 詳細については、「 [tchar. h の汎用テキストマップ](../text/generic-text-mappings-in-tchar-h.md)」を参照してください。

  - MBCS の下で文字列を解析する場合は、注意が必要です。 Unicode では、これらの予防措置は必要ありません。 詳細については、「 [MBCS プログラミングのヒント](../text/mbcs-programming-tips.md)」を参照してください。

  - アプリケーションで ANSI (8 ビット) と Unicode (16 ビット) 文字を混在させる場合は注意が必要です。 プログラムの一部では ANSI 文字を使用し、他の部分では Unicode 文字を使用することができますが、同じ文字列に混在させることはできません。

  - アプリケーションに文字列をハードコーディングしないでください。 代わりに、それらをアプリケーションの .rc ファイルに追加して、STRINGTABLE リソースにします。 これにより、ソースコードの変更や再コンパイルを必要とせずに、アプリケーションをローカライズできます。 STRINGTABLE リソースの詳細については、「 [文字列エディター](../windows/string-editor.md)」を参照してください。

> [!NOTE]
> ヨーロッパと MBCS の文字セットには、文字コードとして0x80 文字を超える文字が含まれています。 ほとんどのコードでは、符号付き文字が使用されるため、0x80 を超えるこれらの文字は、に変換されるときに符号拡張され **`int`** ます。 これは、符号拡張文字 (負の値) が配列の外側にあるため、配列のインデックス作成に問題があります。 日本語など、MBCS を使用する言語も一意です。 文字は1バイトまたは2バイトで構成される可能性があるため、常に両方のバイトを同時に操作する必要があります。

## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[国際化戦略](../text/internationalization-strategies.md)
