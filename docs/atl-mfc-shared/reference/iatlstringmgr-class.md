---
description: '詳細情報: IAtlStringMgr クラス'
title: IAtlStringMgr クラス
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: 7b3aa9d8984639d42e673e96b5fcf25308a757bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166526"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr クラス

このクラスは、メモリマネージャーへのインターフェイスを表し `CStringT` ます。

## <a name="syntax"></a>構文

```
__interface IAtlStringMgr
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[割当て](#allocate)|新しい文字列データ構造体を割り当てるには、このメソッドを呼び出します。|
|[複製](#clone)|このメソッドを呼び出して、の別のインスタンスで使用する新しい文字列マネージャーへのポインターを返し `CSimpleStringT` ます。|
|[Free](#free)|文字列データ構造体を解放するには、このメソッドを呼び出します。|
|[GetNilString](#getnilstring)|`CStringData`空の文字列オブジェクトによって使用されるオブジェクトへのポインターを返します。|
|[再割り当て](#reallocate)|文字列データ構造体を再割り当てするには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

このインターフェイスは、MFC に依存しない文字列クラスによって使用されるメモリを管理します。たとえば、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)などです。

このクラスを使用して、カスタム文字列クラスのカスタムメモリマネージャーを実装することもできます。 詳細については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atl. h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a> IAtlStringMgr:: Allocate

新しい文字列データ構造体を割り当てます。

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>パラメーター

*nAllocLength*<br/>
新しいメモリブロック内の文字数。

*nCharSize*<br/>
文字列マネージャーによって使用される文字型のサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

> [!NOTE]
> 例外をスローすることによって、割り当ての失敗を通知しません。 代わりに、NULL を返すことによって、失敗した割り当てを通知する必要があります。

### <a name="remarks"></a>解説

[IAtlStringMgr:: Free](#free)または[IAtlStringMgr::](#reallocate)の再割り当てを呼び出して、このメソッドによって割り当てられたメモリを解放します。

> [!NOTE]
> 使用例については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="iatlstringmgrclone"></a><a name="clone"></a> IAtlStringMgr:: Clone

の別のインスタンスで使用する新しい文字列マネージャーへのポインターを返し `CSimpleStringT` ます。

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>戻り値

`IAtlStringMgr` オブジェクトのコピーが返されます。

### <a name="remarks"></a>解説

新しい文字列に文字列マネージャーが必要な場合に、フレームワークによって一般に呼び出されます。 ほとんどの場合、 **`this`** ポインターが返されます。

ただし、メモリマネージャーがの複数のインスタンスでの使用をサポートしていない場合は、 `CSimpleStringT` 共有可能な文字列マネージャーへのポインターを返す必要があります。

> [!NOTE]
> 使用例については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="iatlstringmgrfree"></a><a name="free"></a> IAtlStringMgr:: Free

文字列データ構造体を解放します。

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
解放されるメモリブロックへのポインター。

### <a name="remarks"></a>解説

[割り当て](#allocate)または再[割り当て](../../atl/reference/iatlmemmgr-class.md#reallocate)によって以前に割り当てられた、指定されたメモリブロックを解放します。

> [!NOTE]
> 使用例については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a> IAtlStringMgr::GetNilString

空の文字列の文字列データ構造へのポインターを返します。

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>戻り値

空の文字列を `CStringData` 表すために使用されるオブジェクトへのポインター。

### <a name="remarks"></a>解説

空の文字列の表現を返すには、この関数を呼び出します。

> [!NOTE]
> カスタム文字列マネージャーを実装する場合、この関数は失敗しないようにする必要があります。 これを確認するには、のインスタンスを `CNilStringData` string manager クラスに埋め込み、そのインスタンスへのポインターを返します。

> [!NOTE]
> 使用例については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a> IAtlStringMgr:: 再割り当て

文字列データ構造体を再割り当てします。

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
このメモリマネージャーによって以前に割り当てられたメモリへのポインター。

*nAllocLength*<br/>
新しいメモリブロック内の文字数。

*nCharSize*<br/>
文字列マネージャーによって使用される文字型のサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

*PData* によって指定された既存のメモリブロックのサイズを変更するには、この関数を呼び出します。

[IAtlStringMgr:: free](#free)を呼び出して、このメソッドによって割り当てられたメモリを解放します。

> [!NOTE]
> 使用例については、「 [メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
