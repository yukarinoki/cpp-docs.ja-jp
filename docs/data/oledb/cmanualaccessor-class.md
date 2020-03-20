---
title: CManualAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
ms.openlocfilehash: 80c8f94a417c700f86159de53bd53e4011f78d71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546069"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor クラス

高度な使用を目的として設計されたアクセサー型を表します。

## <a name="syntax"></a>構文

```cpp
class CManualAccessor : public CAccessorBase
```

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[AddBindEntry](#addbindentry)|出力列にバインドエントリを追加します。|
|[AddParameterEntry](#addparameterentry)|パラメーターアクセサーにパラメーターエントリを追加します。|
|[CreateAccessor](#createaccessor)|列バインド構造にメモリを割り当て、列データメンバーを初期化します。|
|[CreateParameterAccessor](#createparameteraccessor)|パラメーターバインド構造体にメモリを割り当て、パラメーターデータメンバーを初期化します。|

## <a name="remarks"></a>コメント

`CManualAccessor`を使用すると、実行時の関数呼び出しによってパラメーターと出力列のバインドを指定できます。

## <a name="cmanualaccessoraddbindentry"></a><a name="addbindentry"></a>CManualAccessor:: AddBindEntry

出力列にバインドエントリを追加します。

### <a name="syntax"></a>構文

```cpp
void AddBindEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL) throw ();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
から列番号。

*wType*<br/>
からデータ型。

*nColumnSize*<br/>
から列のサイズ (バイト単位)。

*pData*<br/>
からバッファーに格納されている列データへのポインター。

*pLength*<br/>
から必要に応じて、フィールド長へのポインター。

*pStatus*<br/>
から必要に応じて、列の状態にバインドする変数へのポインター。

### <a name="remarks"></a>コメント

この関数を使用するには、最初に[Createaccessor](../../data/oledb/cmanualaccessor-createaccessor.md)を呼び出す必要があります。 `CreateAccessor`で指定された列数よりも多くのエントリを追加することはできません。

## <a name="cmanualaccessoraddparameterentry"></a><a name="addparameterentry"></a>CManualAccessor:: AddParameterEntry

パラメーターエントリをパラメーターエントリ構造体に追加します。

### <a name="syntax"></a>構文

```cpp
void AddParameterEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL,
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 」を参照してください。

*nOrdinal*<br/>
からパラメーター番号。

*wType*<br/>
からデータ型。

*nColumnSize*<br/>
から列のサイズ (バイト単位)。

*pData*<br/>
からバッファーに格納されている列データへのポインター。

*pLength*<br/>
から必要に応じて、フィールド長へのポインター。

*pStatus*<br/>
から必要に応じて、列の状態にバインドする変数へのポインター。

*eParamIO*<br/>
からバインドが関連付けられているパラメーターが入力、入力、出力、または出力パラメーターであるかどうかを指定します。

### <a name="remarks"></a>コメント

この関数を使用するには、最初に[Createparameteraccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)を呼び出す必要があります。

## <a name="cmanualaccessorcreateaccessor"></a><a name="createaccessor"></a>CManualAccessor:: CreateAccessor

列バインド構造にメモリを割り当て、列データメンバーを初期化します。

### <a name="syntax"></a>構文

```cpp
HRESULT CreateAccessor(int nBindEntries,
  void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>パラメーター

*nBindEntries*<br/>
から列の数。 この数値は、 [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)関数の呼び出し回数と一致している必要があります。

*pBuffer*<br/>
から出力列が格納されるバッファーへのポインター。

*nBufferSize*<br/>
からバッファーのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

`CManualAccessor::AddBindEntry` 関数を呼び出す前に、この関数を呼び出します。

## <a name="cmanualaccessorcreateparameteraccessor"></a><a name="createparameteraccessor"></a>CManualAccessor:: CreateParameterAccessor

パラメーターバインド構造体にメモリを割り当て、パラメーターデータメンバーを初期化します。

### <a name="syntax"></a>構文

```cpp
HRESULT CreateParameterAccessor(int nBindEntries,
   void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>パラメーター

*nBindEntries*<br/>
から列の数。

*pBuffer*<br/>
から入力列が格納されるバッファーへのポインター。

*nBufferSize*<br/>
からバッファーのサイズ (バイト単位)。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>コメント

[Addparameterentry](../../data/oledb/cmanualaccessor-addparameterentry.md)を呼び出す前に、この関数を呼び出す必要があります。

## <a name="see-also"></a>参照

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor クラス](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)