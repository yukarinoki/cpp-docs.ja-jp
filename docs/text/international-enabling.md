---
title: 国際化対応について |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f4edcae610f17409c319c7b4bd39dc137e1211e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858703"
---
# <a name="international-enabling"></a>国際化対応について
従来のほとんどの C および C++ コードによって、国際対応のアプリケーションに対して適切に動作しない文字と文字列の操作に関する仮定を行います。 MFC とランタイム ライブラリの両方は、Unicode や MBCS をサポートしてが、まだ作業を行うには このセクションで Visual C の「国際化対応」の意味について説明します。  
  
-   両方の Unicode と MBCS MFC 関数のパラメーター リストでの移植性のデータ型を使用して有効にし、型を返します。 これらの型が、ビルドがシンボルを定義するかどうかに応じて、適切な方法で条件付きで定義されている **_UNICODE**または記号 **_MBCS** (つまり、DBCS)。 MFC ライブラリの別のバリエーションは、アプリケーションを使用して、ビルドの定義によってこれら 2 つの記号のうち自動的にリンクします。  
  
-   クラス ライブラリのコードでは、ポータブルのランタイム関数とその他の手段を使用して Unicode や MBCS が正常に動作します。  
  
-   コードで特定の種類の国際化タスクを処理する必要がありますも。  
  
    -   MFC のいずれの環境に移植性を高める同じポータブルのランタイム関数を使用します。  
  
    -   リテラル文字列と文字いずれの環境では、移植性を高めるを使用して、 **_T**マクロです。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
    -   Mbcs 文字列を解析するときに、予防策をとります。 Unicode では、これらの予防措置は必要ありません。 詳細については、次を参照してください。 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)です。  
  
    -   注意して、アプリケーションで ANSI (8 ビット)、Unicode (16 ビット) 文字が混在する場合。 プログラムの一部の ANSI 文字と、他のユーザーに Unicode 文字を使用することは、同じ文字列内に混在させることはできません。  
  
    -   アプリケーションで文字列をハードコーディングしないをしないでください。 代わりに、できるように STRINGTABLE リソースをアプリケーションの .rc ファイルに追加します。 アプリケーションは、ソース コードの変更や再コンパイルを必要とせず、ローカライズできます。 STRINGTABLE リソースに関する詳細については、次を参照してください。[ストリング エディター](../windows/string-editor.md)です。  
  
> [!NOTE]
>  ヨーロッパと MBCS 文字セットでは、文字コードが 0x80 より大きい、アクセント付き文字など、一部の文字があります。 ほとんどのコードは、符号付き文字を使用しているためこれらの文字 0x80 よりも大きい値は符号拡張に変換される`int`です。 これは、配列の外側、符号拡張文字の文字列、負の場合、インデックスを作成するための配列のインデックスの問題です。 日本語などの MBCS を使用する言語も一意です。 文字は、1 つまたは 2 バイトで構成されている可能性があります、ため常に同時に両方のバイトを操作する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [国際化のアプローチ](../text/internationalization-strategies.md)