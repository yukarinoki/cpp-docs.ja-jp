---
description: '詳細情報: CStringData クラス'
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
ms.openlocfilehash: 74bf3563cb5dca506498ceef05ddc84f13c44f41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166591"
---
# <a name="cstringdata-class"></a>CStringData クラス

このクラスは、文字列オブジェクトのデータを表します。

## <a name="syntax"></a>構文

```
struct CStringData
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[AddRef](#addref)|文字列データオブジェクトの参照カウントをインクリメントします。|
|[data](#data)|文字列オブジェクトの文字データを取得します。|
|[IsLocked](#islocked)|関連付けられた文字列オブジェクトのバッファーがロックされているかどうかを判断します。|
|[IsShared](#isshared)|関連付けられている文字列オブジェクトのバッファーが現在共有されているかどうかを判断します。|
|[[Lock] (ロック)](#lock)|関連付けられている文字列オブジェクトのバッファーをロックします。|
|[リリース](#release)|指定した文字列オブジェクトを解放します。|
|[Unlock](#unlock)|関連付けられている文字列オブジェクトのバッファーのロックを解除します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|[nAllocLength](#nalloclength)|S で割り当てられたデータの長さ `XCHAR` (終端の null は含まない)|
|[nDataLength](#ndatalength)|内で現在使用されているデータの長さ `XCHAR` (終端の null は含まない)|
|[nRefs](#nrefs)|オブジェクトの現在の参照カウント。|
|[pStringMgr](#pstringmgr)|この文字列オブジェクトの文字列マネージャーへのポインター。|

## <a name="remarks"></a>解説

このクラスは、カスタム文字列マネージャーを実装する開発者によってのみ使用されます。 カスタム文字列マネージャーの詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md) 」を参照してください。

このクラスは、 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) オブジェクトなど、より上位の文字列オブジェクトに関連付けられているさまざまな種類の情報とデータをカプセル化します。 上位のすべての string オブジェクトには、関連付けられたオブジェクトへのポインターが含まれてい `CStringData` ます。これにより、複数の string オブジェクトが同じ文字列データオブジェクトを指すことができます。 このリレーションシップは、オブジェクトの参照カウント () によって表され `nRefs` `CStringData` ます。

> [!NOTE]
> 場合によっては、文字列型 (など) は、複数 `CFixedString` の上位の文字列オブジェクトと文字列データオブジェクトを共有しません。 詳細については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

このデータは次のもので構成されます。

- 文字列のメモリマネージャー ( [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)型)。

- 文字列の現在の長さ ( [Ndatalength](#ndatalength))。

- 文字列の割り当てられた長さ ( [nAllocLength](#nalloclength))。 パフォーマンス上の理由から、これは現在の文字列の長さと異なる場合があります。

- オブジェクトの現在の参照カウント ( [Nrefs](#nrefs)) `CStringData` 。 この値は、同じオブジェクトを共有する文字列オブジェクトの数を決定するために使用され `CStringData` ます。

- 文字列の実際の文字バッファー ( [データ](#data))。

   > [!NOTE]
   > 文字列オブジェクトの実際の文字バッファーは文字列マネージャーによって割り当てられ、オブジェクトに追加され `CStringData` ます。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="cstringdataaddref"></a><a name="addref"></a> CStringData:: AddRef

文字列オブジェクトの参照カウントをインクリメントします。

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>解説

文字列オブジェクトの参照カウントをインクリメントします。

> [!NOTE]
> 負の数は文字列バッファーがロックされていることを示すため、負の値を持つ文字列に対してこのメソッドを呼び出さないでください。

## <a name="cstringdatadata"></a><a name="data"></a> CStringData: ata:d

文字列オブジェクトの文字バッファーへのポインターを返します。

```cpp
void* data() throw();
```

### <a name="return-value"></a>戻り値

文字列オブジェクトの文字バッファーへのポインター。

### <a name="remarks"></a>解説

この関数を呼び出して、関連付けられている文字列オブジェクトの現在の文字バッファーを返します。

> [!NOTE]
> このバッファーは、オブジェクトによって割り当てられるのではなく、 `CStringData` 必要に応じて文字列マネージャーによって割り当てられます。 割り当てられた場合、バッファーは文字列データオブジェクトに追加されます。

## <a name="cstringdataislocked"></a><a name="islocked"></a> CStringData:: IsLocked

文字バッファーがロックされているかどうかを判断します。

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>戻り値

バッファーがロックされている場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

文字列オブジェクトの文字バッファーが現在ロックされているかどうかを判断するには、この関数を呼び出します。

## <a name="cstringdataisshared"></a><a name="isshared"></a> CStringData::IsShared

文字バッファーが共有されているかどうかを判断します。

```
bool IsShared() const throw();
```

### <a name="return-value"></a>戻り値

バッファーが共有されている場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

文字列データオブジェクトの文字バッファーが現在複数の文字列オブジェクト間で共有されているかどうかを判断するには、この関数を呼び出します。

## <a name="cstringdatalock"></a><a name="lock"></a> CStringData:: Lock

関連付けられている文字列オブジェクトの文字バッファーをロックします。

```cpp
void Lock() throw();
```

### <a name="remarks"></a>解説

文字列データオブジェクトの文字バッファーをロックするには、この関数を呼び出します。 ロックとロック解除は、文字バッファーへの直接アクセスが開発者に必要な場合に使用されます。 ロックの例としては、の [Lockbuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) メソッドと [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) メソッドが挙げられ `CSimpleStringT` ます。

> [!NOTE]
> バッファーが上位の文字列オブジェクト間で共有されていない場合にのみ、文字バッファーをロックできます。

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a> CStringData::nAllocLength

割り当てられた文字バッファーの長さ。

```
int nAllocLength;
```

### <a name="remarks"></a>解説

割り当てられたデータバッファーの長さを s に格納し `XCHAR` ます (終端の null は含まれません)。

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a> CStringData:: nDataLength

文字列オブジェクトの現在の長さ。

```
int nDataLength;
```

### <a name="remarks"></a>解説

現在使用されているデータの長さを s に格納 `XCHAR` します (終端の null は含まれません)。

## <a name="cstringdatanrefs"></a><a name="nrefs"></a> CStringData:: nRefs

文字列データオブジェクトの参照カウント。

```
long nRefs;
```

### <a name="remarks"></a>解説

文字列データオブジェクトの参照カウントを格納します。 この数は、文字列データオブジェクトに関連付けられている上位の文字列オブジェクトの数を示します。 負の値は、文字列データオブジェクトが現在ロックされていることを示します。

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a> CStringData::p StringMgr

関連付けられている文字列オブジェクトのメモリマネージャー。

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>解説

関連付けられている文字列オブジェクトのメモリマネージャーを格納します。 メモリマネージャーと文字列の詳細については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="cstringdatarelease"></a><a name="release"></a> CStringData:: Release

文字列データオブジェクトの参照カウントをデクリメントします。

```cpp
void Release() throw();
```

### <a name="remarks"></a>解説

参照カウントをデクリメントし、 `CStringData` 参照カウントがゼロになった場合に構造体を解放するには、この関数を呼び出します。 これは、通常、文字列オブジェクトが削除され、その結果、文字列データオブジェクトを参照する必要がなくなった場合に実行されます。

たとえば、次のコードは、 `CStringData::Release` に関連付けられている文字列データオブジェクトに対してを呼び出し `str1` ます。

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a> CStringData:: Unlock

関連付けられている文字列オブジェクトの文字バッファーのロックを解除します。

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>解説

文字列データオブジェクトの文字バッファーのロックを解除するには、この関数を呼び出します。 バッファーのロックが解除されると、そのバッファーは共有可能になり、参照カウントされる可能性があります。

> [!NOTE]
> への各呼び出しは `Lock` 、対応するへの呼び出しによって照合される必要があり `Unlock` ます。

ロックとロック解除は、開発者が文字列データを共有しないようにする必要がある場合に使用します。 ロックの例としては、の [Lockbuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) メソッドと [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) メソッドが挙げられ `CSimpleStringT` ます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
