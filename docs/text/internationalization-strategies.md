---
description: 詳細については、「国際化戦略」を参照してください。
title: 国際化のアプローチ
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
ms.openlocfilehash: 51570a3e340a8af0a9f16f8212aa11f6bf3119b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331188"
---
# <a name="internationalization-strategies"></a>国際化のアプローチ

ターゲットのオペレーティングシステムと市場に応じて、いくつかの国際化戦略があります。

- アプリケーションで Unicode を使用している。

   Unicode 固有の機能を使用し、すべての文字は16ビット幅です (ただし、特殊な目的で、プログラムの一部で ANSI 文字を使用できます)。 C ランタイムライブラリには、Unicode のみのプログラミングで使用できる関数、マクロ、およびデータ型が用意されています。 MFC は完全に Unicode に対応しています。

- アプリケーションは MBCS を使用し、任意の Win32 プラットフォームで実行できます。

   MBCS 固有の機能を使用します。 文字列には、1バイト文字、2バイト文字、またはその両方を含めることができます。 C ランタイムライブラリには、MBCS のみのプログラミングのための関数、マクロ、およびデータ型が用意されています。 MFC は完全に MBCS に対応しています。

- アプリケーションのソースコードは完全な移植性を確保するために記述されています。シンボルまたは定義されたシンボルを使用して再コンパイルすることにより `_UNICODE` `_MBCS` 、いずれかを使用するバージョンを生成できます。 詳細については、「 [tchar. h の汎用テキストマップ](../text/generic-text-mappings-in-tchar-h.md)」を参照してください。

   完全に移植可能な C ランタイム関数、マクロ、およびデータ型を使用します。 MFC の柔軟性は、これらの方法のいずれかをサポートしています。

これらのトピックの残りの部分では、Unicode または MBCS として作成できる、完全に移植可能なコードの記述に焦点を当てています。

## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[ロケールとコードページ](../text/locales-and-code-pages.md)
