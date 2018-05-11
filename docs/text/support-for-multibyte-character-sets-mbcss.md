---
title: マルチバイト文字セット (Mbcs) のサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b0381b570cbf9e900d44ac075876e63b6be14a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>マルチバイト文字セット (MBCS) のサポート
マルチバイト文字セット (MBCS: Multibyte Character Set) は、日本語や中国語など、1 バイト文字では表現できない文字セットをサポートするニーズに対する古いアプローチです。 新規開発を行う場合は、エンド ユーザーに対して表示されることのないシステム文字列を除き、すべてのテキスト文字列で Unicode 文字列を使用する必要があります。 MBCS は、レガシ テクノロジであり、新規開発にはお勧めしません。  
  
 最も一般的な MBCS の実装は、2 バイト文字セット (DBCS: Double-Byte Character Set) です。 Visual C++ と MFC では、DBCS に完全に対応しています。  
  
 サンプルについては、MFC ソース コード ファイルを参照してください。  
  
 大きな文字セットを採用している市場に対応したプラットフォームでは、Unicode の代わりとしては MBCS がまず考えられます。 MFC では、国際化に対応できるデータ型と C ランタイム関数を使用することにより MBCS をサポートしています。 プログラム コードでもこれらを使用するようにしてください。  
  
 MBCS では、1 バイトまたは 2 バイトのいずれかで文字がエンコードされます。 2 バイト文字では、最初にくる先頭バイトとその後ろに続くバイトの両方で 1 つの文字と解釈されるようになっています。 この最初のバイトは、先行バイト用に予約されている範囲の値をとります。 バイトのどの範囲が先行バイトとなるかは、使用するコード ページによって異なります。 たとえば、日本語のコード ページ 932 では 0x81 から 0x9F までの範囲を先行バイトとして使いますが、韓国語のコード ページ 949 では別の範囲を使っています。  
  
 MBCS のプログラミングでは、次の点について考慮する必要があります。  
  
 環境で使われる MBCS 文字  
 MBCS 文字は、ファイル名やフォルダー名などの文字列に使用できます。  
  
 編集操作  
 MBCS アプリケーションでの編集操作は、バイトではなく文字に対して行う必要があります。 カレットで文字を分割しないでください。右方向キーでは、右へ 1 文字移動します。 **削除**; 文字を削除する必要があります**を元に戻す**再挿入する必要があります。  
  
 文字列操作  
 MBCS を使うアプリケーションでは、文字列操作で特殊な問題が出てきます。 1 つの文字列の中に 1 バイト幅の文字と 2 バイト幅の文字が混在しているため、先頭バイトがあるかどうかを必ず確認する必要があります。  
  
 ランタイム ライブラリのサポート  
 C のランタイム ライブラリおよび MFC は、1 バイト文字、MBCS、および Unicode でのプログラミングをそれぞれサポートしています。 1 バイトの文字列に処理できる、`str`と対応するファミリのランタイム関数、MBCS 文字列に処理できる`_mbs`関数、および Unicode 文字列が対応するを持つ処理*wcs*関数。 MFC クラスのメンバー関数では、状況に応じて、通常の `str` ファミリの関数、MBCS の関数、または Unicode の関数に割り当てる移植性の高いランタイム関数を使用しています。  
  
 MBCS と Unicode の移植性  
 Tchar.h ヘッダー ファイルを使用することにより、同じソースから 1 バイト、MBCS、および Unicode の各アプリケーションをビルドできます。 Tchar.h の付いたマクロが定義されて *_tcs*にマップする`str`、 `_mbs`、または*wcs*機能を必要に応じて、します。 MBCS をビルドするシンボルを定義する **_MBCS**です。 Unicode をビルドするシンボルを定義する **_UNICODE**です。 既定では、 **_MBCS** MFC アプリケーションに対して定義されています。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
> [!NOTE]
>  両方を定義する場合の動作が定義されていない **_UNICODE**と **_MBCS**です。  
  
 Mbctype.h ヘッダー ファイルおよび Mbstring.h ヘッダー ファイルでは、MBCS 固有の関数とマクロが定義されています。この関数とマクロは状況に応じて必要になります。 たとえば `_ismbblead` は、文字列の特定のバイトが先行バイトかどうかを示します。  
  
 国際対応の移植性を使用してプログラムのコード[Unicode](../text/support-for-unicode.md)またはマルチバイト文字セット (Mbcs)。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [MBCS をプログラムで有効にします。](../text/international-enabling.md)  
  
-   [プログラムで Unicode と MBCS の両方を有効にします。](../text/internationalization-strategies.md)  
  
-   [MBCS を使用して、国際化プログラムを作成するには](../text/mbcs-programming-tips.md)  
  
-   [MBCS プログラミングの概要を参照してください。](../text/mbcs-programming-tips.md)  
  
-   [バイト幅の移植性に対する汎用テキスト マップの詳細します。](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>関連項目  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)   
 [Visual C++ における MBCS のサポート](../text/mbcs-support-in-visual-cpp.md)