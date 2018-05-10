---
title: 'CFixedStringT: 例、カスタム文字列マネージャーの |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f841124fd12497fdb4dd4b813de2d803e43ff60b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: 例のカスタム文字列マネージャー
クラスによって使用されるカスタム文字列マネージャーの一例を実装する、ATL ライブラリ[CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)という**CFixedStringMgr**です。 `CFixedStringT` 派生した[CStringT](../atl-mfc-shared/reference/cstringt-class.md)の一部としてその文字データを割り当てる文字列を実装して、`CFixedStringT`オブジェクト自体が、文字列で指定された長さよりも小さい場合に限り、 **t_nChars**テンプレート パラメーター`CFixedStringT`です。 この方法で、文字列必要はありませんヒープ、文字列の長さが固定バッファーのサイズを超えない限り、します。 `CFixedStringT`限りませんを使用して、文字列データを割り当てるヒープを使用できません**CAtlStringMgr**その文字列マネージャーとして。 カスタム文字列マネージャーを使用して (**CFixedStringMgr**)、実装、 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md)インターフェイスです。 このインターフェイスは、後ほど[マネージャーの実装、カスタム文字列 (高度な方法)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)です。  
  
 コンス トラクター **CFixedStringMgr**は 3 つのパラメーターを受け取ります。  
  
-   **pData:** 固定へのポインター`CStringData`構造を使用します。  
  
-   **文字数:** 文字の最大数、`CStringData`構造体に格納できます。  
  
-   **pMgr:** へのポインター、 `IAtlStringMgr` 「バックアップ文字列マネージャー」のインターフェイス  
  
 コンス トラクターの値を格納する`pData`と**pMgr**内の各メンバー変数 (`m_pData`と**m_pMgr**)。 値がゼロに固定バッファーと、参照カウントを-1 の最大サイズに等しい長さの使用可能なバッファーの長さを設定します。 参照カウントの値は、バッファーがロックされていることを示しますのこのインスタンスを使用して**CFixedStringMgr**文字列マネージャーとして。  
  
 その他のロックされているバッファーのマークを付けるように`CStringT`インスタンスを保持するバッファーへの参照を共有します。 他の`CStringT`インスタンスは、バッファーのバッファーに含まれる可能性があります共有が許可された`CFixedStringT`中に、その他の文字列バッファーを使用していて削除します。  
  
 **CFixedStringMgr**の完全な実装は、`IAtlStringMgr`インターフェイスです。 各メソッドの実装は、個別に説明しています。  
  
## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr::Allocate の実装  
 実装**CFixedStringMgr::Allocate**文字列の要求されたサイズが固定バッファーのサイズ以下かどうかを最初に確認し (に格納されている、`m_pData`メンバー)。 場合は、固定バッファーの大きさが、 **CFixedStringMgr**長さ 0 の固定バッファーをロックします。 文字列の長さが固定のバッファーのサイズを超えて大きくならない限り、`CStringT`バッファーの再割り当てする必要はありません。  
  
 文字列の要求されたサイズは固定バッファーより大きいかどうか**CFixedStringMgr**バックアップ文字列マネージャーに要求を転送します。 バックアップ文字列マネージャーは、ヒープからバッファーを割り当てと見なされます。 このバッファーを返す前に、ただし、 **CFixedStringMgr** 、バッファーをロックし、バッファーの文字列のマネージャーのポインターをへのポインターに置き換え、 **CFixedStringMgr**オブジェクト。 これにより、再割り当てしたりしてバッファーを解放しようとする`CStringT`呼び出せるは**CFixedStringMgr**です。  
  
## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr::ReAllocate の実装  
 実装**CFixedStringMgr::ReAllocate**の実装に非常に似ています**Allocate**です。  
  
 再割り当てされるバッファーは固定バッファーでは、要求されたバッファー サイズは固定バッファーよりも小さい場合は、割り当ては行われません。 ただし、再割り当てされるバッファーが固定バッファーでない場合、バックアップ マネージャーに割り当てられるバッファーをする必要があります。 ここではバックアップ マネージャーは、バッファーの再割り当てに使用されます。  
  
 再割り当てされるバッファーは固定バッファーと固定バッファーに収まるように、新しいバッファー サイズが大きすぎる場合**CFixedStringMgr**バックアップ マネージャーを使用して新しいバッファーを割り当てます。 固定バッファーの内容は新しいバッファーにコピーされます。  
  
## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr::Free の実装  
 実装**CFixedStringMgr::Free**と同様のパターンに依存して**Allocate**と`ReAllocate`です。 固定バッファーが解放されるバッファーには、メソッドにより、長さ 0 のロックされているバッファーに設定します。 バックアップ マネージャーで解放されているバッファーが割り当てられた場合**CFixedStringMgr**バックアップ マネージャーを使用して、それを解放します。  
  
## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr::Clone の実装  
 実装**CFixedStringMgr::Clone**常にバックアップ マネージャーへのポインターを返しますではなく、 **CFixedStringMgr**自体です。 これは、ためのすべてのインスタンス**CFixedStringMgr**の 1 つのインスタンスに関連付けできる`CStringT`です。 その他のインスタンスの`CStringT`マネージャーの複製を行おうとする必要がありますバックアップ マネージャーの代わりに表示します。 これは、バックアップ マネージャーは、共有されることをサポートしているためです。  
  
## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr::GetNilString の実装  
 実装**CFixedStringMgr::GetNilString**固定バッファーを返します。 1 対 1 対応のため**CFixedStringMgr**と`CStringT`の特定のインスタンス`CStringT`一度に 1 つ以上のバッファーを使用しません。 したがって、nil 文字列と実際の文字列バッファーことはありません、同時に必要です。  
  
 固定バッファーが、使用されていないときに**CFixedStringMgr**長さが 0 でそれが初期化されていることを確認します。 これにより、nil の文字列として使用することができます。 追加の利点として、`nAllocLength`固定バッファーのメンバーは常に固定バッファー全体のサイズに設定します。 つまり、`CStringT`呼び出さずに文字列を拡大できる[IAtlStringMgr::Reallocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)nil の文字列の場合でも、します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cstringt.h  
  
## <a name="see-also"></a>関連項目  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

