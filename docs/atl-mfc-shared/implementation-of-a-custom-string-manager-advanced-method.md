---
description: '詳細情報: カスタム文字列マネージャーの実装 (高度なメソッド)'
title: カスタム文字列マネージャー (高度なメソッド) の実装
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 042c0759076d14e2fd0cf8dd91e34c4f1d8bb534
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166968"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>カスタム文字列マネージャー (高度なメソッド) の実装

特殊な状況では、メモリの割り当てに使用されるヒープを変更するだけでなく、カスタム文字列マネージャーを実装することもできます。 このような場合は、 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) インターフェイスをカスタム文字列マネージャーとして手動で実装する必要があります。

これを行うには、まず、 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) がそのインターフェイスを使用して文字列データを管理する方法を理解する必要があります。 のすべてのインスタンスには、 `CStringT` [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) 構造体へのポインターがあります。 この可変長構造体には、文字列に関する重要な情報 (長さなど) と、文字列の実際の文字データが含まれています。 すべてのカスタム文字列マネージャーは、の要求でこれらの構造体の割り当てと解放を行い `CStringT` ます。

`CStringData`構造体は、次の4つのフィールドで構成されます。

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) このフィールドは、 `IAtlStringMgr` この文字列データを管理するために使用されるインターフェイスを指します。 `CStringT`が文字列バッファーを再割り当てまたは解放する必要がある場合は、このインターフェイスの再割り当てまたは解放メソッドを呼び出し、 `CStringData` 構造体をパラメーターとして渡します。 `CStringData`文字列マネージャーで構造体を割り当てるときは、カスタム文字列マネージャーをポイントするようにこのフィールドを設定する必要があります。

- [Ndatalength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) このフィールドには、バッファーに格納されている文字列の現在の論理長 (終端の null を除く) が含まれます。 `CStringT` 文字列の長さが変更されたときに、このフィールドを更新します。 構造体を割り当てるとき `CStringData` は、文字列マネージャーがこのフィールドを0に設定する必要があります。 構造体を再割り当てする場合 `CStringData` 、カスタム文字列マネージャーはこのフィールドを変更せずに残しておく必要があります。

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) このフィールドには、再割り当てせずにこの文字列バッファーに格納できる最大文字数 (終端の null を除く) が含まれています。 `CStringT`が文字列の論理的な長さを増やす必要がある場合は、常にこのフィールドをチェックして、バッファー内に十分な領域があることを確認してください。 チェックが失敗した場合、 `CStringT` カスタム文字列マネージャーを呼び出してバッファーを再割り当てします。 構造体を割り当てたり再割り当てしたりする場合は `CStringData` 、このフィールドに少なくとも *nchars* パラメーターで要求されている文字数を [IAtlStringMgr:: Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate) または [IAtlStringMgr:: 再割り当て](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)に設定する必要があります。 要求されたサイズよりもバッファーに空き領域がある場合は、この値を設定して、使用可能な実際の空き領域を反映できます。 これにより、が文字列 `CStringT` マネージャーにコールバックしてバッファーを再割り当てする前に、割り当てられた領域全体を占めるように文字列を拡張できます。

- [Nrefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) このフィールドには、文字列バッファーの現在の参照カウントが格納されます。 値が1の場合、の1つのインスタンス `CStringT` がバッファーを使用します。 さらに、インスタンスは、バッファーの内容の読み取りと変更の両方を行うことができます。 値が1より大きい場合、の複数のインスタンスで `CStringT` バッファーを使用できます。 文字バッファーは共有されるため、 `CStringT` インスタンスはバッファーの内容のみを読み取ることができます。 コンテンツを変更するには、 `CStringT` まずバッファーのコピーを作成します。 値が負の場合は、の1つのインスタンスだけ `CStringT` がバッファーを使用します。 この場合、バッファーはロックされていると見なされます。 `CStringT`インスタンスがロックされたバッファーを使用している場合、の他のインスタンスは `CStringT` バッファーを共有できません。 代わりに、これらのインスタンスは、内容を操作する前にバッファーのコピーを作成します。 また、 `CStringT` ロックされたバッファーを使用するインスタンスは、割り当てられている他のインスタンスのバッファーを共有しません `CStringT` 。 この場合、インスタンスは、ロックされ `CStringT` たバッファーに他の文字列をコピーします。

   構造体を割り当てるときは、 `CStringData` バッファーに許可されている共有の種類を反映するようにこのフィールドを設定する必要があります。 ほとんどの実装では、この値を1に設定します。 これにより、通常のコピー時の書き込み共有動作が可能になります。 ただし、文字列マネージャーが文字列バッファーの共有をサポートしていない場合は、このフィールドを locked 状態に設定します。 これにより、は、 `CStringT` 割り当てられたのインスタンスに対してのみこのバッファーを使用し `CStringT` ます。

## <a name="see-also"></a>関連項目

[CStringT を使用したメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)
