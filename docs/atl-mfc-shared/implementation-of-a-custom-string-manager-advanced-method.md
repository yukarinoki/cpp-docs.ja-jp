---
title: マネージャーの実装、カスタム文字列 (メソッドの詳細) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23798a4e3c1a5d3c46ea28dec39b37697aae640f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357816"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>マネージャーの実装、カスタム文字列 (高度な方法)
特殊な状況では、メモリの割り当てに使用されるヒープを変更する以上の処理をカスタム文字列マネージャーを実装することができます。 この場合、手動で実装する必要あります、 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md)カスタム文字列マネージャーとインターフェイスします。  
  
 これを行うためには理解しておく必要がどのように[CStringT](../atl-mfc-shared/reference/cstringt-class.md)そのインターフェイスを使用して、文字列データを管理します。 すべてのインスタンス`CStringT`へのポインターを持つ、 [CStringData](../atl-mfc-shared/reference/cstringdata-class.md)構造体。 この可変長の構造体には、文字列の実際の文字データだけでなく、文字列 (長さ) などに関する重要な情報が含まれています。 すべてのカスタム文字列マネージャーは割り当てと解放の要求でこれらの構造体を`CStringT`です。  
  
 `CStringData`構造体は、4 つのフィールドを構成します。  
  
-   [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr)このフィールドを指す、`IAtlStringMgr`文字列データを管理するためのインターフェイスです。 ときに`CStringT`再割り当てまたは再割り当てまたは渡すこと、このインターフェイスの無料のメソッド呼び出し文字列バッファーを解放する必要があります、`CStringData`をパラメーターとして構造体。 割り当てるときに、`CStringData`構造文字列マネージャーで、カスタム文字列マネージャー をポイントするには、このフィールドを設定する必要があります。  
  
-   [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength)このフィールドには、現在の論理終端の null を除く、バッファーに格納された文字列の長さが含まれています。 `CStringT` 文字列の長さが変更されたときに、このフィールドを更新します。 割り当てるときに、`CStringData`構造は、文字列マネージャー必要があります設定このフィールドをゼロにします。 再割り当て時、`CStringData`構造体では、このフィールドを変更しないが、カスタム文字列マネージャーに残す必要があります。  
  
-   [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength)このフィールドには、文字の最大数 (終端の null を除く) に再割り当てすることがなくこの文字列バッファーに格納できるが含まれています。 たびに`CStringT`論理、文字列の長さを拡張する必要がありますまずバッファー内に十分な領域があることを確認するには、このフィールドをチェックします。 チェックが失敗した場合、`CStringT`カスタム文字列マネージャーの呼び出しは、バッファーの再割り当ています。 割り当てまたは再割り当て時に、`CStringData`構造は、する必要があります設定このフィールドには、少なくともで要求されている文字の数、**文字数**パラメーターを[IAtlStringMgr::Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate)または[IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)です。 要求よりも、バッファー内でより多くの領域がある場合は、使用可能な領域の実際の容量を反映するようにこの値を設定することができます。 これにより、`CStringT`バッファーの再割り当てする文字列マネージャーにコールバックする前に、文字列全体を占めるを拡張する領域を割り当てられています。  
  
-   [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs)このフィールドには、文字列バッファーの現在の参照カウントが含まれています。 値が場合、1 つの単一インスタンス`CStringT`バッファーを使用しています。 さらに、インスタンスは読み取りし、バッファーの内容の変更の両方を許可します。 値が 1 より大きい場合の複数のインスタンス`CStringT`バッファーを使用することができます。 文字バッファーが共有されるため、`CStringT`インスタンスは、バッファーの内容のみを読み取ることができます。 内容を変更する`CStringT`最初、バッファーのコピーを作成します。 場合は、値が負の値、1 つだけの`CStringT`バッファーを使用しています。 この場合、バッファーと見なされますがロックされています。 ときに、`CStringT`インスタンスは、バッファーを使用して、ロックの他のインスタンスがない`CStringT`バッファーを共有することがあります。 代わりに、これらのインスタンスは、内容を操作する前に、バッファーのコピーを作成します。 さらに、`CStringT`ロックされているバッファーを使用して、インスタンスはその他のバッファーを共有しようとはしません`CStringT`に割り当てられているインスタンス。 ここで、`CStringT`インスタンスがロックされているバッファーに他の文字列をコピーします。  
  
     割り当てるときに、`CStringData`構造は、バッファーが使用できる共有の種類を反映するようにこのフィールドを設定する必要があります。 ほとんどの実装のためには、いずれかにこの値を設定します。 これにより、一般的な共有コピー オン ライト動作できます。 ただし、文字列の上司が文字列バッファーの共有をサポートしていない場合は、ロックの状態をこのフィールドを設定します。 これにより、`CStringT`のみのインスタンスにこのバッファーを使用する`CStringT`割り当てられていること。  
  
## <a name="see-also"></a>関連項目  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

