---
description: '詳細については、「CFixedStringT: カスタム文字列マネージャーの例」を参照してください。'
title: 'CFixedStringT: カスタム文字列マネージャーの例'
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: c9af2530500ad5972c01d063116e7ac981109493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142507"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT: カスタム文字列マネージャーの例

ATL ライブラリは、 **CFixedStringMgr** というクラス [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)によって使用されるカスタム文字列マネージャーの1つの例を実装します。 `CFixedStringT` は [CStringT](../atl-mfc-shared/reference/cstringt-class.md) から派生し、 `CFixedStringT` 文字列がのテンプレートパラメーターで指定された長さよりも小さい限り、その文字データをオブジェクト自体の一部として割り当てる文字列を実装し `t_nChars` `CFixedStringT` ます。 この方法では、文字列の長さが固定バッファーのサイズを超えていない限り、文字列はヒープをまったく必要としません。 `CFixedStringT`は常にヒープを使用して文字列データを割り当てないため、を `CAtlStringMgr` 文字列マネージャーとして使用することはできません。 カスタム文字列マネージャー () を使用して `CFixedStringMgr` 、 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) インターフェイスを実装します。 このインターフェイスについては [、「カスタム文字列マネージャー (高度なメソッド) の実装](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)」で説明しています。

のコンストラクターは、 `CFixedStringMgr` 次の3つのパラメーターを受け取ります。

- *pData:*`CStringData`使用する固定構造体へのポインター。

- *Nchars:*`CStringData`構造体が保持できる最大文字数。

- *Pmgr:*`IAtlStringMgr`"バックアップ文字列マネージャー" のインターフェイスへのポインター。

コンストラクターは、 *pData* と *pmgr* の値をそれぞれのメンバー変数 (および) に格納し `m_pData` `m_pMgr` ます。 次に、バッファーの長さを0に、使用可能な長さを固定バッファーの最大サイズと同じに設定し、参照カウントを-1 に設定します。 [参照カウント] の値は、バッファーがロックされていることを示し、のこのインスタンスを `CFixedStringMgr` 文字列マネージャーとして使用します。

バッファーをロック済みとしてマークすると、他のインスタンスがその `CStringT` バッファーへの共有参照を保持できなくなります。 他の `CStringT` インスタンスがバッファーの共有を許可されていた場合、に含まれているバッファーは、 `CFixedStringT` 他の文字列がまだバッファーを使用している間に削除される可能性があります。

`CFixedStringMgr` は、インターフェイスの完全な実装です `IAtlStringMgr` 。 各メソッドの実装については、個別に説明します。

## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr:: Allocate の実装

の実装では、 `CFixedStringMgr::Allocate` 最初に、要求された文字列のサイズが (メンバーに格納されている) 固定バッファーのサイズ以下であるかどうかを確認し `m_pData` ます。 固定バッファーが十分な大きさの場合は、 `CFixedStringMgr` 固定バッファーを長さ0でロックします。 文字列の長さが固定バッファーのサイズを超えない限り、はバッファーを再 `CStringT` 割り当てする必要はありません。

要求された文字列のサイズが固定バッファーより大きい場合は、 `CFixedStringMgr` バックアップ文字列マネージャーに要求を転送します。 バックアップ文字列マネージャーは、ヒープからバッファーを割り当てることを想定しています。 ただし、このバッファーを返す前にバッファーを `CFixedStringMgr` ロックし、バッファーの文字列マネージャーポインターをオブジェクトへのポインターに置き換え `CFixedStringMgr` ます。 これにより、がを呼び出すことにより、バッファーの再割り当てまたは解放を試みること `CStringT` が `CFixedStringMgr` できます。

## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr:: 再割り当ての実装

の実装は、の実装と非常によく似てい `CFixedStringMgr::ReAllocate` `Allocate` ます。

再割り当てされるバッファーが固定バッファーで、要求されたバッファーサイズが固定バッファーよりも小さい場合、割り当ては行われません。 ただし、再割り当てされるバッファーが固定バッファーでない場合は、バックアップマネージャーで割り当てられたバッファーである必要があります。 この場合、バックアップマネージャーを使用してバッファーを再割り当てします。

再割り当てされるバッファーが固定バッファーで、新しいバッファーサイズが大きすぎて固定バッファーに格納できない場合、は `CFixedStringMgr` バックアップマネージャーを使用して新しいバッファーを割り当てます。 次に、固定バッファーの内容を新しいバッファーにコピーします。

## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr:: Free の実装

の実装は、 `CFixedStringMgr::Free` とと同じパターンに従い `Allocate` `ReAllocate` ます。 解放されるバッファーが固定バッファーの場合、メソッドは長さが0のロックされたバッファーに設定します。 解放されるバッファーがバックアップマネージャーで割り当てられている場合、は `CFixedStringMgr` バックアップマネージャーを使用してそれを解放します。

## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr:: Clone の実装

の実装は、 `CFixedStringMgr::Clone` 常にではなくバックアップマネージャーへのポインターを返し `CFixedStringMgr` ます。 これは、のすべてのインスタンスを `CFixedStringMgr` の1つのインスタンスのみに関連付けることができるため `CStringT` です。 マネージャーを複製し `CStringT` ようとするその他のインスタンスは、代わりにバックアップマネージャーを取得する必要があります。 これは、backup manager が共有をサポートしているためです。

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr:: GetNilString の実装

の実装は `CFixedStringMgr::GetNilString` 、固定バッファーを返します。 との1対1の対応によって `CFixedStringMgr` `CStringT` 、の特定のインスタンスが一度に複数の `CStringT` バッファーを使用することはありません。 そのため、nil 文字列と実際の文字列バッファーは同時に必要ありません。

固定バッファーが使用されていない場合、は常に `CFixedStringMgr` ゼロの長さで初期化されることを保証します。 これにより、nil 文字列として使用できるようになります。 おまけとして、 `nAllocLength` 固定バッファーのメンバーは常に固定バッファーの完全なサイズに設定されます。 これは、が `CStringT` nil 文字列の場合でも、 [IAtlStringMgr:: 再割り当て](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)を呼び出さずに文字列を拡張できることを意味します。

## <a name="requirements"></a>要件

**ヘッダー:** cstringt

## <a name="see-also"></a>関連項目

[CStringT を使用したメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)
