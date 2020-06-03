---
title: 国際化対応について
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: b6c645bafef87ed0b2d43903f4752ef659d79f89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375799"
---
# <a name="international-enabling"></a>国際化対応について

従来の C および C++ コードのほとんどは、国際化アプリケーションではうまく機能しない文字操作と文字列操作を前提としています。 MFC とランタイム ライブラリの両方が Unicode または MBCS をサポートしていますが、作業はまだあります。 ここでは、Visual C++ での "国際対応" の意味について説明します。

- Unicode と MBCS の両方は、MFC 関数パラメーター リストと戻り値の型で移植可能なデータ型を使用して有効になります。 これらの型は、ビルドでシンボル`_UNICODE`を定義するかシンボル`_MBCS`(つまり DBCS) を定義するかによって、適切な方法で条件付きで定義されます。 MFC ライブラリの異なるバリアントは、ビルドで定義されるこれら 2 つのシンボルに応じて、アプリケーションに自動的にリンクされます。

- クラス ライブラリ コードでは、ポータブルランタイム関数やその他の方法を使用して、Unicode または MBCS の動作を正しく行います。

- コード内で特定の種類の国際化タスクを処理する必要があります。

  - どちらの環境でも、MFC を移植可能にするのと同じポータブルランタイム関数を使用します。

  - マクロを使用して、いずれかの環境でリテラル文字列と文字`_T`を移植可能にします。 詳細については、 [tchar.h の汎用テキスト マッピングを](../text/generic-text-mappings-in-tchar-h.md)参照してください。

  - MBCS で文字列を解析する場合は、注意を要します。 これらの予防措置は Unicode では必要ありません。 詳細については[、「MBCS プログラミングのヒント](../text/mbcs-programming-tips.md)」を参照してください。

  - アプリケーションで ANSI (8 ビット) 文字と Unicode (16 ビット) 文字を混在させ、注意してください。 プログラムの一部で ANSI 文字を使用し、他の部分では Unicode 文字を使用することは可能ですが、同じ文字列に混在させることはできません。

  - アプリケーションで文字列をハードコーディングしないでください。 代わりに、アプリケーションの .rc ファイルに追加して、リソースを STRINGTABLE にします。 ソース コードの変更や再コンパイルを必要とせずに、アプリケーションをローカライズできます。 STRINGTABLE リソースの詳細については、「[文字列エディタ](../windows/string-editor.md)」を参照してください。

> [!NOTE]
> ヨーロッパ文字セットと MBCS 文字セットには、アクセント付き文字など、文字コードが 0x80 より大きい文字が含まれるものがあります。 ほとんどのコードでは符号付き文字を使用するため、0x80 より大きい文字は**int**に変換されるときに符号拡張されます。符号拡張文字が負の値であるため、配列のインデックス作成では問題になります。 日本語などの MBCS を使用する言語も一意です。 文字は 1 バイトまたは 2 バイトで構成される場合があるため、常に両方のバイトを同時に操作する必要があります。

## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[国際化のアプローチ](../text/internationalization-strategies.md)
