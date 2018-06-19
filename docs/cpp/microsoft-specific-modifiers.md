---
title: Microsoft 固有の修飾子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8490a50f30d366a53a9e3288417a8d83032c556d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420224"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft 固有の修飾子
このセクションでは、次の領域での C++ への Microsoft 固有の拡張について説明します。  
  
-   [ベース アドレス指定](../cpp/based-addressing.md)、他のポインターをオフセットできるベースとしてのポインターの使用の推奨事項  
  
-   [関数の呼び出し規約](../cpp/calling-conventions.md)  
  
-   拡張ストレージ クラス属性で宣言された、 [_ _declspec](../cpp/declspec.md)キーワード  
  
-   [_ _W64](../cpp/w64.md)キーワード  
  
 Microsoft 固有キーワードの多くは、宣言子を変更して派生型を作成する際に使用できます。 宣言子の詳細については、次を参照してください。[宣言子](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)です。  
  
### <a name="microsoft-specific-keywords"></a>Microsoft 固有キーワード  
  
|キーワード|説明|派生型を作成するために使用しますか?|  
|-------------|-------------|---------------------------------|  
|[__based](../cpp/based-grammar.md)|これに続く名前は、宣言に含まれている 32 ビット ベースへの 32 ビット オフセットを宣言します。|[はい]|  
|[__cdecl](../cpp/cdecl.md)|これに続く名前は、C の命名規約と呼び出し規則を使用します。|[はい]|  
|[__declspec](../cpp/declspec.md)|これに続く名前は、Microsoft 固有のストレージ クラス属性を指定します。|×|  
|[__fastcall](../cpp/fastcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、レジスタ (使用できる場合) を使用できる関数を宣言します。|[はい]|  
|[__restrict](../cpp/extension-restrict.md)|_ _Declspec に似ています ([制限](../cpp/restrict.md)) が変数で使用します。|×|  
|[__stdcall](../cpp/stdcall.md)|これに続く名前は、標準呼び出し規則を順守する関数を指定します。|[はい]|  
|[__w64](../cpp/w64.md)|64 ビット コンパイラでより大きいデータ型としてマークします。|×|  
|[__unaligned](../cpp/unaligned.md)|型またはその他のデータへのポインターが配置されていないことを指定します。|×|  
|[__vectorcall](../cpp/vectorcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、SSE レジスタを含むレジスタ (使用できる場合) を使用できる関数を宣言します。|[はい]|  
  
## <a name="see-also"></a>関連項目  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)