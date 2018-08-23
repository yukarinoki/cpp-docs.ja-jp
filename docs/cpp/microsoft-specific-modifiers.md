---
title: Microsoft 固有の修飾子 |Microsoft Docs
ms.custom: ''
ms.date: 08/16/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3dfc57e1d6af11628b37823f2452ee2b65f8a7f
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "42572519"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft 固有の修飾子
このセクションでは、次の領域での C++ への Microsoft 固有の拡張について説明します。  
  
-   [ベース アドレス指定](based-addressing.md)、他のポインターをオフセットできるベースとしてのポインターを使用すること  
  
-   [関数の呼び出し規則](calling-conventions.md)  
  
-   拡張ストレージ クラスの属性で宣言された、 [_ _declspec](declspec.md)キーワード  
  
-   [_ _W64](w64.md)キーワード  

### <a name="microsoft-specific-keywords"></a>Microsoft 固有キーワード  

Microsoft 固有キーワードの多くは、宣言子を変更して派生型を作成する際に使用できます。 宣言子の詳細については、次を参照してください。[宣言子](overview-of-declarators.md)します。  

|キーワード|説明|派生型を作成するために使用しますか?|   
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|これに続く名前は、宣言に含まれている 32 ビット ベースへの 32 ビット オフセットを宣言します。|[はい]|   
|[__cdecl](cdecl.md)|これに続く名前は、C の命名規約と呼び出し規則を使用します。|[はい]|      
|[__declspec](declspec.md)|これに続く名前は、Microsoft 固有のストレージ クラス属性を指定します。|いいえ|    
|[__fastcall](fastcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、レジスタ (使用できる場合) を使用できる関数を宣言します。|[はい]|   
|[__restrict](extension-restrict.md)|_ _Declspec に似ています ([制限](restrict.md)) が変数で使用します。|いいえ|      
|[__stdcall](stdcall.md)|これに続く名前は、標準呼び出し規則を順守する関数を指定します。|[はい]|     
|[__w64](w64.md)|64 ビット コンパイラでより大きいデータ型としてマークします。|いいえ|    
|[__unaligned](unaligned.md)|型またはその他のデータへのポインターが配置されていないことを指定します。|いいえ|      
|[__vectorcall](vectorcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、SSE レジスタを含むレジスタ (使用できる場合) を使用できる関数を宣言します。|[はい]|      
    
## <a name="see-also"></a>関連項目     
 [C++ 言語リファレンス](cpp-language-reference.md)