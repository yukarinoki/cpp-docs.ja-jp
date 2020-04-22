---
title: CStringData クラス
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: f14f1d9c269f06099bd224f582de1f55da33ff0f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746840"
---
# <a name="cstringdata-class"></a>CStringData クラス

このクラスは、文字列オブジェクトのデータを表します。

## <a name="syntax"></a>構文

```
struct CStringData
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddRef](#addref)|文字列データ オブジェクトの参照カウントをインクリメントします。|
|[データ](#data)|文字列オブジェクトの文字データを取得します。|
|[IsLocked](#islocked)|関連付けられた文字列オブジェクトのバッファがロックされているかどうかを判断します。|
|[IsShared](#isshared)|関連付けられた文字列オブジェクトのバッファが現在共有されているかどうかを判断します。|
|[[Lock] (ロック)](#lock)|関連付けられた文字列オブジェクトのバッファーをロックします。|
|[リリース](#release)|指定した文字列オブジェクトを解放します。|
|[ロック 解除](#unlock)|関連付けられた文字列オブジェクトのバッファをロック解除します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|[長さ](#nalloclength)|s 内の割り`XCHAR`当てられたデータの長さ (終端 NULL を含まない)|
|[長さ](#ndatalength)|s 内で現在使用`XCHAR`されているデータの長さ (終端 NULL を含まない)|
|[n参照](#nrefs)|オブジェクトの現在の参照カウント。|
|[をクリックします。](#pstringmgr)|この文字列オブジェクトの文字列マネージャーへのポインター。|

## <a name="remarks"></a>解説

このクラスは、カスタム文字列マネージャーを実装する開発者のみが使用する必要があります。 カスタム文字列マネージャーの詳細については、[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

このクラスは[、CStringT 、CSimpleStringT、CFixedStringT](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトなど、より[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)高い文字列オブジェクトに関連[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)付けられたさまざまな種類の情報とデータをカプセル化します。 すべての上位の文字列オブジェクトには、関連付けられた`CStringData`オブジェクトへのポインターが含まれているため、複数の文字列オブジェクトが同じ文字列データオブジェクトを指すことができます。 この関係は、`nRefs``CStringData`オブジェクトの参照カウント ( ) で表されます。

> [!NOTE]
> 場合によっては、文字列型 ( など`CFixedString`) は、複数の上位の文字列オブジェクトと文字列データオブジェクトを共有しません。 詳細については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

このデータは、次の要素で構成されます。

- 文字列のメモリ マネージャー [(IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)型) です。

- 文字列の現在の長さ ( [nDataLength](#ndatalength)) を指定します。

- 文字列の割り当てられた長さ ( [nAllocLength](#nalloclength)) 。 パフォーマンス上の理由から、現在の文字列の長さとは異なる場合があります。

- `CStringData`オブジェクトの現在の参照カウント ( [nRefs](#nrefs)) です。 この値は、同じ`CStringData`オブジェクトを共有している文字列オブジェクトの数を決定するときに使用されます。

- 文字列の実際の文字バッファー ([データ](#data)) です。

   > [!NOTE]
   > 文字列オブジェクトの実際の文字バッファーは、文字列マネージャーによって割り当てられ、オブジェクトに`CStringData`追加されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpstr.h

## <a name="cstringdataaddref"></a><a name="addref"></a>を使用します。

文字列オブジェクトの参照カウントをインクリメントします。

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>解説

文字列オブジェクトの参照カウントをインクリメントします。

> [!NOTE]
> 負のカウントは文字列バッファーがロックされていることを示すため、負の参照カウントを持つ文字列に対してこのメソッドを呼び出しません。

## <a name="cstringdatadata"></a><a name="data"></a>:dタータ

文字列オブジェクトの文字バッファーへのポインターを返します。

```cpp
void* data() throw();
```

### <a name="return-value"></a>戻り値

文字列オブジェクトの文字バッファーへのポインター。

### <a name="remarks"></a>解説

関連付けられた文字列オブジェクトの現在の文字バッファーを返します。

> [!NOTE]
> このバッファは`CStringData`、オブジェクトによって割り当てられませんが、必要に応じて文字列マネージャによって割り当てられます。 割り当てられると、バッファーは文字列データ オブジェクトに追加されます。

## <a name="cstringdataislocked"></a><a name="islocked"></a>を指定します。

文字バッファーがロックされているかどうかを判断します。

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>戻り値

バッファーがロックされている場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーが現在ロックされているかどうかを調べます。

## <a name="cstringdataisshared"></a><a name="isshared"></a>を使用します。

文字バッファーが共有されているかどうかを判断します。

```
bool IsShared() const throw();
```

### <a name="return-value"></a>戻り値

バッファーが共有されている場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

文字列データ オブジェクトの文字バッファーが現在複数の文字列オブジェクト間で共有されているかどうかを調べます。

## <a name="cstringdatalock"></a><a name="lock"></a>ロック

関連付けられた文字列オブジェクトの文字バッファーをロックします。

```cpp
void Lock() throw();
```

### <a name="remarks"></a>解説

文字列データ オブジェクトの文字バッファーをロックします。 ロックとロック解除は、開発者が文字バッファーに直接アクセスする必要がある場合に使用されます。 ロックの良い例は、[のロック バッファ](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)メソッドと[ロック バッファロック メソッド](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)によって示されています。 `CSimpleStringT`

> [!NOTE]
> 文字バッファーは、バッファーが上位のストリング・オブジェクト間で共有されていない場合にのみロックできます。

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a>を返します。

割り当てられた文字バッファーの長さ。

```
int nAllocLength;
```

### <a name="remarks"></a>解説

割り当てられたデータ バッファの長さを`XCHAR`s に格納します (終端 null は含まれません)。

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a>データを返します。

文字列オブジェクトの現在の長さ。

```
int nDataLength;
```

### <a name="remarks"></a>解説

現在使用されているデータの長さを`XCHAR`s に格納します (終端 null は含まれません)。

## <a name="cstringdatanrefs"></a><a name="nrefs"></a>を返します。

文字列データ オブジェクトの参照カウント。

```
long nRefs;
```

### <a name="remarks"></a>解説

文字列データ オブジェクトの参照カウントを格納します。 このカウントは、文字列データ オブジェクトに関連付けられている、より大きい文字列オブジェクトの数を示します。 負の値は、文字列データ オブジェクトが現在ロックされていることを示します。

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a>:p文字列を返します。

関連付けられた文字列オブジェクトのメモリ マネージャー。

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>解説

関連付けられた文字列オブジェクトのメモリ マネージャーを格納します。 メモリ マネージャと文字列の詳細については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="cstringdatarelease"></a><a name="release"></a>::リリース

文字列データ オブジェクトの参照カウントをデクリメントします。

```cpp
void Release() throw();
```

### <a name="remarks"></a>解説

参照カウントがゼロに達した場合に構造体を`CStringData`解放して、参照カウントを減らします。 これは通常、文字列オブジェクトが削除された場合に行われるため、文字列データオブジェクトを参照する必要がなくなります。

たとえば、次のコードは、`CStringData::Release`に関連付けられた`str1`文字列データ オブジェクトを呼び出します。

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a>ロック解除

関連付けられた文字列オブジェクトの文字バッファーのロックを解除します。

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>解説

文字列データ オブジェクトの文字バッファーをロック解除します。 いったんロックが解除されると、そのバッファは共有可能になり、参照カウントが可能になります。

> [!NOTE]
> の`Lock`各呼び出しは、 への対応`Unlock`する呼び出しと一致する必要があります。

ロックとロック解除は、開発者が文字列データを共有しないようにする必要がある場合に使用されます。 ロックの良い例は、[のロック バッファ](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)メソッドと[ロック バッファロック メソッド](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)によって示されています。 `CSimpleStringT`

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
