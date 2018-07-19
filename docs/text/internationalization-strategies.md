---
title: 国際対応戦略 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20e4d7b067daedcbc5ce065c096e561dbf932ac1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856597"
---
# <a name="internationalization-strategies"></a>国際化のアプローチ
ターゲット オペレーティング システムと市場、に応じていくつかの国際対応戦略がある場合。  
  
-   アプリケーションで Unicode を使用します。  
  
     Unicode 固有の機能を使用して、(プログラムの一部の ANSI 文字を使用するには特別な目的で) には、すべての文字が 16 ビット幅。 C ランタイム ライブラリは、Unicode 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、完全に Unicode に対応します。  
  
-   アプリケーションでは、MBCS を使用し、任意の Win32 プラットフォームで実行できます。  
  
     MBCS 固有の機能を使用するとします。 文字列には、1 バイト文字、2 バイト文字、またはその両方を含めることができます。 C ランタイム ライブラリは、MBCS 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、MBCS に対応しています。  
  
-   移植性を高めるのため、アプリケーションのソース コードが記述された — シンボルの再コンパイルして **_UNICODE**または記号 **_MBCS**定義されている、いずれかを使用するバージョンを生成できます。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
     完全に移植できる C ランタイム関数、マクロ、およびデータ型を使用するとします。 MFC の柔軟性は、これらの方法のいずれかをサポートします。  
  
 これらのトピックの残りの部分は、Unicode と MBCS をビルドすると完全に移植可能なコードの作成に集中できます。  
  
## <a name="see-also"></a>関連項目  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [ロケールとコード ページ](../text/locales-and-code-pages.md)