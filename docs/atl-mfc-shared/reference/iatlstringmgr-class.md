---
title: クラス
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
ms.openlocfilehash: c3fabb7a7a6da4129787d219bd83b2a35fa0c4dd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746606"
---
# <a name="iatlstringmgr-class"></a>クラス

このクラスは、メモリ マネージャ`CStringT`へのインターフェイスを表します。

## <a name="syntax"></a>構文

```
__interface IAtlStringMgr
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[割り当てる](#allocate)|新しい文字列データ構造体を割り当てます。|
|[複製](#clone)|の別のインスタンスで使用する新しい文字列マネージャーへのポインターを返`CSimpleStringT`します。|
|[Free](#free)|文字列データ構造体を解放します。|
|[ゲットニルストリング](#getnilstring)|空の文字列オブジェクトが`CStringData`使用するオブジェクトへのポインターを返します。|
|[再割り当て](#reallocate)|文字列データ構造体を再割り当てします。|

## <a name="remarks"></a>解説

このインターフェイスは、MFC に依存しない文字列クラスで使用されるメモリを管理します。などの[CSimpleStringT、CStringT、](../../atl-mfc-shared/reference/csimplestringt-class.md)および[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)。 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)

このクラスを使用して、カスタム文字列クラスのカスタム メモリ マネージャーを実装することもできます。 詳細については、「[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpstr.h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a>イタトルストリングMgr::割り当て

新しい文字列データ構造体を割り当てます。

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>パラメーター

*長さ*<br/>
新しいメモリ ブロック内の文字数。

*nCharサイズ*<br/>
文字列マネージャーが使用する文字タイプのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

> [!NOTE]
> 例外をスローして、割り当てに失敗したことを通知しないでください。 代わりに、失敗した割り当ては、NULL を返すことによってシグナルされます。

### <a name="remarks"></a>解説

呼び出し[IAtlStringMgr::Free](#free)または[IAtlStringMgr::この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

> [!NOTE]
> 使用例については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::クローン

の別のインスタンスで使用する新しい文字列マネージャーへのポインターを`CSimpleStringT`返します。

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>戻り値

`IAtlStringMgr` オブジェクトのコピーが返されます。

### <a name="remarks"></a>解説

新しい文字列に文字列マネージャーが必要な場合に、フレームワークによって一般的に呼び出されます。 ほとんどの場合 **、this**ポインターが返されます。

ただし、メモリ マネージャーが の複数の`CSimpleStringT`インスタンスでの使用をサポートしていない場合は、共有可能な文字列マネージャーへのポインターを返す必要があります。

> [!NOTE]
> 使用例については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="iatlstringmgrfree"></a><a name="free"></a>イアットルストリングムグラム::無料

文字列データ構造体を解放します。

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>パラメーター

*Pdata*<br/>
解放されるメモリ ブロックへのポインター。

### <a name="remarks"></a>解説

Allocate または再[割り当て](#allocate)によって以前に割り当てられた指定されたメモリ ブロック[を](../../atl/reference/iatlmemmgr-class.md#reallocate)解放します。

> [!NOTE]
> 使用例については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>イアトルストリングムグラム::ゲットニルストリング

空の文字列の文字列データ構造体へのポインターを返します。

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>戻り値

空の文字列を`CStringData`表すために使用するオブジェクトへのポインター。

### <a name="remarks"></a>解説

空の文字列の表現を返します。

> [!NOTE]
> カスタム文字列マネージャーを実装する場合、この関数は失敗しません。 これを確認するには、文字列マネージャークラス`CNilStringData`にインスタンスを埋め込み、そのインスタンスへのポインターを返します。

> [!NOTE]
> 使用例については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a>再割り当て

文字列データ構造体を再割り当てします。

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>パラメーター

*Pdata*<br/>
このメモリ マネージャによって以前に割り当てられたメモリへのポインタ。

*長さ*<br/>
新しいメモリ ブロック内の文字数。

*nCharサイズ*<br/>
文字列マネージャーが使用する文字タイプのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

*pData*で指定された既存のメモリ ブロックのサイズを変更します。

呼び出し[IAtlStringMgr::この](#free)メソッドによって割り当てられたメモリを解放するフリー。

> [!NOTE]
> 使用例については、「[メモリ管理」および「CStringT」](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
