---
title: クラスを一覧表示します。
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 0a7fd781c63e4ea084cf078e49fc9efb9cfa2d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326788"
---
# <a name="cinterfacelist-class"></a>クラスを一覧表示します。

このクラスは、COM インターフェイス ポインターのリストを構築するときに役立つメソッドを提供します。

## <a name="syntax"></a>構文

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*私*<br/>
格納するポインターの型を指定する COM インターフェイス。

*ピッド*<br/>
I の IID への*ポインタ。*

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[一覧::C インターフェイスリスト](#cinterfacelist)|インターフェイス リストのコンストラクター。|

## <a name="remarks"></a>解説

このクラスは、COM インターフェイス ポインターのリストを作成するためのコンストラクターと派生メソッドを提供します。 配列が必要な場合は[、CInterfaceArray](../../atl/reference/cinterfacearray-class.md)を使用します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[カトルリスト](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a>一覧::C インターフェイスリスト

インターフェイス リストのコンストラクター。

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロック サイズ (既定値は 10)。

### <a name="remarks"></a>解説

ブロック サイズは、新しい要素が必要なときに割り当てられるメモリの量を測定します。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。

## <a name="see-also"></a>関連項目

[クラスを表します。](../../atl/reference/catllist-class.md)<br/>
[CComQIPtrクラス](../../atl/reference/ccomqiptr-class.md)<br/>
[クラスをクラス](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
