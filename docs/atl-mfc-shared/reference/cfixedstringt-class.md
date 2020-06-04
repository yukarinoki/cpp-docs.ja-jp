---
title: クラスを固定
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: fe096185f6f0b71ad45757cd0b75ab13c41e5f5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317828"
---
# <a name="cfixedstringt-class"></a>クラスを固定

このクラスは、固定文字バッファーを持つ文字列オブジェクトを表します。

## <a name="syntax"></a>構文

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>パラメーター

*文字列型*<br/>
固定文字列オブジェクトの基本クラスとして使用され、任意`CStringT`のベース型を指定できます。 たとえば`CString`、 、 `CStringA`、`CStringW`などがあります。

*t_nChars*<br/>
バッファーに格納されている文字数。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#cfixedstringt)|文字列オブジェクトのコンストラクター。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を指定します。](#operator_eq)|オブジェクトに新しい値を`CFixedStringT`割り当てます。|

## <a name="remarks"></a>解説

このクラスは、 に基づくカスタム文字列クラスの`CStringT`例です。 似ていますが、実装では 2 つのクラスが異なります。 の主な違`CFixedStringT`い`CStringT`は次のとおりです。

- 初期文字バッファーはオブジェクトの一部として割り当てられ、サイズは*t_nChars。* これにより、オブジェクト`CFixedString`はパフォーマンス上の目的で連続したメモリ チャンクを占有できます。 ただし、`CFixedStringT`オブジェクトの内容が*t_nChars*を超えて大きくなると、バッファーは動的に割り当てられます。

- `CFixedStringT`オブジェクトの文字バッファーは常に同じ長さ *(t_nChars)* です。 `CStringT`オブジェクトのバッファ サイズに制限はありません。

- のメモリ マネージャ`CFixedStringT`は、複数の`CFixedStringT`オブジェクト間で[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)オブジェクトを共有することが許可されていないカスタマイズされています。 `CStringT`オブジェクトにはこの制限はありません。

文字列オブジェクトの`CFixedStringT`カスタマイズと一般的なメモリ管理の詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>必要条件

**ヘッダー:** cstringt.h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>をクリックします。

`CFixedStringT` オブジェクトを構築します。

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
この`CFixedStringT`オブジェクトにコピーされる null で終わる文字列。

*ストルスク*<br/>
この`CFixedStringT`オブジェクト`CFixedStringT`にコピーされる既存のオブジェクト。

*をクリックします。*<br/>
`CFixedStringT`オブジェクトのメモリ マネージャーへのポインター。 のメモリ管理と`IAtlStringMgr`メモリ管理の`CFixedStringT`詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

### <a name="remarks"></a>解説

コンストラクターは、入力データを新しく割り当てられた記憶域にコピーするため、メモリ例外が発生する可能性があることに注意してください。 これらのコンストラクタの中には、変換関数として機能するものもあります。

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a>を指定します。

既存`CFixedStringT`のオブジェクトを新しいデータで再初期化します。

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>パラメーター

*pszSrc*<br/>
この`CFixedStringT`オブジェクトにコピーされる null で終わる文字列。

*ストルスク*<br/>
この`CFixedStringT`オブジェクト`CFixedStringT`にコピーされる既存のオブジェクト。

### <a name="remarks"></a>解説

割り当て演算子を使用すると、結果`CFixedStringT`のオブジェクトを保持するために新しい記憶域が割り当てられることが多いため、メモリ例外が発生する可能性があることに注意してください。

## <a name="see-also"></a>関連項目

[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
