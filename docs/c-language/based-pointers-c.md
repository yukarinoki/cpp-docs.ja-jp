---
title: ベース ポインター (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b414110b0f3367c2b589f82915f417ea7389d738
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="based-pointers-c"></a>ベース ポインター (C)
**Microsoft 固有の仕様**  
  
 [__based (C++ リファレンス)](../cpp/based-pointers-cpp.md)  
  
 Microsoft の 32 ビットおよび 64 ビット C コンパイラでは、based ポインターは 32 ビットまたは 64 ビット ポインター ベースの 32 ビットまたは 64 ビットからのオフセットになります。 ベースとなるアドレス指定は、オブジェクトが割り当てられるセクションを制御して、実行可能ファイルのサイズを小さくし、実行速度を増加させるために役立ちます。 一般に、based ポインターを指定するためのフォームは、次のとおりです。  
  
```  
  
type  
__based(  
base  
)  
declarator  
  
```  
  
 ベースとなるアドレス指定の "ポインター ベース" のバリアントは、ベースとしてのポインターの指定を可能にします。 したがって、based ポインターは、基になっているポインターの先頭から始まるメモリ セクションへのオフセットです。 ポインター アドレスに基づくポインターは、32 ビットおよび 64 ビット コンパイルで有効な `__based` キーワードの唯一の形式です。 このようなコンパイルでは、32 ビットまたは 64 ビット ベースからの、32 ビットまたは 64 ビットのディスプレイスメントになります。  
  
 ポインターに基づいたポインターの使用方法の 1 つは、ポインターを含む永続的な識別子での使用です。 ポインターに基づくポインターで構成されるリンク リストをディスクに保存でき、メモリ内の別の場所に再読み込みしても、ポインターは有効なままです。  
  
 次の例では、ポインターに基づいてポインターを示します。  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 ポインター `vpBuffer` には、プログラムの後の段階で割り当てられるメモリ アドレスが代入されます。 リンク リストは `vpBuffer` の値を基準として再配置されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [宣言子と変数宣言](../c-language/declarators-and-variable-declarations.md)