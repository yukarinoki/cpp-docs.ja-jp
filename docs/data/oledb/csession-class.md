---
description: '詳細情報: CSession クラス'
title: CSession クラス
ms.date: 11/04/2016
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
ms.openlocfilehash: 41ebf1c9d93e1443504f92b052e770c251324633
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268432"
---
# <a name="csession-class"></a>CSession クラス

単一データベースアクセスセッションを表します。

## <a name="syntax"></a>構文

```cpp
class CSession
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[中止](#abort)|トランザクションをキャンセル (終了) します。|
|[閉じる](#close)|セッションを閉じます。|
|[コミット](#commit)|トランザクションをコミットします。|
|[GetTransactionInfo](#gettransactioninfo)|トランザクションに関する情報を返します。|
|[[ファイル]](#open)|データソースオブジェクトの新しいセッションを開きます。|
|[StartTransaction](#starttransaction)|このセッションの新しいトランザクションを開始します。|

## <a name="remarks"></a>解説

1つ以上のセッションを各プロバイダー接続 (データソース) に関連付けることができます。これは、 [CDataSource](../../data/oledb/cdatasource-class.md) オブジェクトによって表されます。 の新しいを作成するには `CSession` `CDataSource` 、 [CSession:: Open](#open)を呼び出します。 データベーストランザクションを開始するには、 `CSession` メソッドを提供し `StartTransaction` ます。 トランザクションが開始されたら、メソッドを使用してコミットするか、メソッドを使用して取り消すことができ `Commit` `Abort` ます。

## <a name="csessionabort"></a><a name="abort"></a> CSession:: Abort

トランザクションを終了します。

### <a name="syntax"></a>構文

```cpp
HRESULT Abort(BOID* pboidReason = NULL,
   BOOL bRetaining = FALSE,
   BOOL bAsync = FALSE) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="csessionclose"></a><a name="close"></a> CSession:: Close

[CSession:: Open](#open)によって開かれたセッションを閉じます。

### <a name="syntax"></a>構文

```cpp
void Close() throw();
```

### <a name="remarks"></a>解説

ポインターを解放 `m_spOpenRowset` します。

## <a name="csessioncommit"></a><a name="commit"></a> CSession:: Commit

トランザクションをコミットします。

### <a name="syntax"></a>構文

```cpp
HRESULT Commit(BOOL bRetaining = FALSE,
   DWORD grfTC = XACTTC_SYNC,
   DWORD grfRM = 0) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

詳細については、「 [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))」を参照してください。

## <a name="csessiongettransactioninfo"></a><a name="gettransactioninfo"></a> CSession:: GetTransactionInfo

トランザクションに関する情報を返します。

### <a name="syntax"></a>構文

```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [ITransaction:: gettransactioninfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

詳細については、 *OLE DB プログラマーリファレンス* の「 [ITransaction:: gettransactioninfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) 」を参照してください。

## <a name="csessionopen"></a><a name="open"></a> CSession:: Open

データソースオブジェクトの新しいセッションを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(const CDataSource& ds,
   DBPROPSET *pPropSet = NULL,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>パラメーター

*ds*<br/>
からセッションを開く対象のデータソース。

*pPropSet*<br/>
から設定するプロパティと値を格納している [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85)) 構造体の配列へのポインター。 Windows SDK の *OLE DB プログラマーリファレンス* の「[プロパティセットとプロパティグループ](/previous-versions/windows/desktop/ms713696(v=vs.85))」を参照してください。

*ulPropSets*<br/>
から *PPropSet* 引数で渡される [DBPROPSET](/previous-versions/windows/desktop/ms714367(v=vs.85))構造体の数。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

に渡す前に、 [CDataSource:: open](./cdatasource-class.md#open) を使用してデータソースオブジェクトを開く必要があり `CSession::Open` ます。

## <a name="csessionstarttransaction"></a><a name="starttransaction"></a> CSession:: StartTransaction

このセッションの新しいトランザクションを開始します。

### <a name="syntax"></a>構文

```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,
   ULONG isoFlags = 0,
   ITransactionOptions* pOtherOptions = NULL,
   ULONG* pulTransactionLevel = NULL) const throw();
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [ITransactionLocal:: starttransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

詳細については、 *OLE DB プログラマーリファレンス* の「 [ITransactionLocal:: starttransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[CatDB](../../overview/visual-cpp-samples.md)<br/>
[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
