---
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
ms.openlocfilehash: 615ad42d5a1e4cb6076877e1d1b5de4bd11fdf83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501323"
---
# <a name="internationalization-strategies"></a>国際化のアプローチ

によって、ターゲットのオペレーティング システムとの市場には、いくつかの国際対応戦略がある場合。

- アプリケーションでは、Unicode を使用します。

   Unicode 固有の機能を使用して、(ただし、プログラムの一部の ANSI 文字を使用するには特別な目的で)、すべての文字が 16 ビット幅。 C ランタイム ライブラリでは、Unicode 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、Unicode に対応しました。

- アプリケーションでは、MBCS を使用し、すべての Win32 プラットフォーム上で実行できます。

   MBCS 固有の機能を使用するとします。 文字列には、1 バイト文字、2 バイト文字、またはその両方を含めることができます。 C ランタイム ライブラリでは、MBCS 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、MBCS に対応しました。

- 完全な移植性のため、アプリケーションのソース コードが記述された、シンボルの再コンパイルして`_UNICODE`または記号`_MBCS`定義されている、いずれかを使用するバージョンを生成できます。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)します。

   完全に移植可能な C ランタイム関数、マクロ、およびデータ型を使用するとします。 MFC の柔軟性は、これらの方法のいずれかをサポートします。

これらのトピックの残りの部分は、Unicode と MBCS をビルドできる完全に移植可能なコードの作成に集中します。

## <a name="see-also"></a>関連項目

[Unicode と MBCS](../text/unicode-and-mbcs.md)<br/>
[ロケールとコード ページ](../text/locales-and-code-pages.md)