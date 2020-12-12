---
description: '詳細情報: CDataConnection クラス'
title: CDataConnection クラス
ms.date: 03/27/2019
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
ms.openlocfilehash: 7cdcb681c40d1ef4e93baee5dc4e4395e6ea9c5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328801"
---
# <a name="cdataconnection-class"></a>CDataConnection クラス

データソースとの接続を管理します。

## <a name="syntax"></a>構文

```cpp
class CDataConnection
```

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[CDataConnection](#cdataconnection)|コンストラクターです。 オブジェクトをインスタンス化し、初期化し `CDataConnection` ます。|
|[コピー](#copy)|既存のデータ接続のコピーを作成します。|
|[[ファイル]](#open)|初期化文字列を使用して、データソースへの接続を開きます。|
|[OpenNewSession](#opennewsession)|現在の接続で新しいセッションを開きます。|

### <a name="operators"></a>オペレーター

| 名前 | 説明 |
|-|-|
|[BOOL 演算子](#op_bool)|現在のセッションが開いているかどうかを判断します。|
|[bool 演算子](#op_bool_ole)|現在のセッションが開いているかどうかを判断します。|
|[operator CDataSource&](#op_cdata_amp)|格納されているオブジェクトへの参照を返し `CDataSource` ます。|
|[operator CDataSource *](#op_cdata_star)|格納されているオブジェクトへのポインターを返し `CDataSource` ます。|
|[operator CSession&](#op_csession_amp)|格納されているオブジェクトへの参照を返し `CSession` ます。|
|[演算子 CSession*](#op_csession_star)|格納されているオブジェクトへのポインターを返し `CSession` ます。|

## <a name="remarks"></a>解説

`CDataConnection` は、クライアントを作成するのに便利なクラスです。これは、必要なオブジェクト (データソースとセッション) と、データソースに接続するときに必要な作業の一部をカプセル化するためです。

を使用しない場合は `CDataConnection` 、オブジェクトを作成し、 `CDataSource` その [OpenFromInitializationString](./cdatasource-class.md#openfrominitializationstring) メソッドを呼び出してから、 [CSession](../../data/oledb/csession-class.md) オブジェクトのインスタンスを作成し、その [Open](./csession-class.md#open) メソッドを呼び出した後、 [CCommand](../../data/oledb/ccommand-class.md) オブジェクトを作成し、その * メソッドを呼び出す必要があり `Open` ます。

では `CDataConnection` 、接続オブジェクトを作成し、初期化文字列を渡してから、その接続を使用してコマンドを開くだけです。 データベースへの接続を繰り返し使用する予定がある場合は、接続を開いたままにしておくことをお勧めします。これには便利な方法が用意されてい `CDataConnection` ます。

> [!NOTE]
> 複数のセッションを処理する必要があるデータベースアプリケーションを作成する場合は、 [Opennewsession](#opennewsession)を使用する必要があります。

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a> CDataConnection:: CDataConnection

オブジェクトをインスタンス化し、初期化し `CDataConnection` ます。

### <a name="syntax"></a>構文

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>パラメーター

*ds*<br/>
から既存のデータ接続への参照。

### <a name="remarks"></a>解説

最初のオーバーライドでは、 `CDataConnection` 既定の設定を使用して新しいオブジェクトを作成します。

2番目のオーバーライドは、指定した `CDataConnection` データ接続オブジェクトと同等の設定で新しいオブジェクトを作成します。

## <a name="cdataconnectioncopy"></a><a name="copy"></a> CDataConnection:: Copy

既存のデータ接続のコピーを作成します。

### <a name="syntax"></a>構文

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>パラメーター

*ds*<br/>
からコピーする既存のデータ接続への参照。

## <a name="cdataconnectionopen"></a><a name="open"></a> CDataConnection:: Open

初期化文字列を使用して、データソースへの接続を開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>パラメーター

*szInitString*<br/>
からデータソースの初期化文字列。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a> CDataConnection:: OpenNewSession

現在の接続オブジェクトのデータソースを使用して、新しいセッションを開きます。

### <a name="syntax"></a>構文

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>パラメーター

*セッション*<br/>
[入力/出力]新しいセッションオブジェクトへの参照。

### <a name="remarks"></a>解説

新しいセッションでは、現在の接続オブジェクトに含まれているデータソースオブジェクトを親として使用し、データソースと同じすべての情報にアクセスできます。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a> CDataConnection:: operator BOOL

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>解説

**BOOL** (MFC typedef) 値を返します。 **TRUE** は、現在のセッションが開いていることを示します。 **FALSE** は、現在のセッションが閉じられていることを示します。

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a> CDataConnection:: operator bool (OLE DB)

現在のセッションが開いているかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
operator bool() throw();
```

### <a name="remarks"></a>解説

**`bool`**(C++ データ型) 値を返します。 **`true`** は、現在のセッションが開いていることを示します。は **`false`** 、現在のセッションが閉じられていることを示します。

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a> CDataConnection:: operator CDataSource&amp;

格納されているオブジェクトへの参照を返し `CDataSource` ます。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれているオブジェクトへの参照を返します。これにより、 `CDataSource` 参照が必要なオブジェクトを渡すことができ `CDataConnection` `CDataSource` ます。

### <a name="example"></a>例

参照を受け取る関数 (次のような関数) がある場合は `func` `CDataSource` 、を使用して `CDataSource&` オブジェクトを渡すことができ `CDataConnection` ます。

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a> CDataConnection:: operator CDataSource *

格納されているオブジェクトへのポインターを返し `CDataSource` ます。

### <a name="syntax"></a>構文

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれているオブジェクトへのポインターを返します。これにより、 `CDataSource` ポインターが必要なオブジェクトを渡すことができ `CDataConnection` `CDataSource` ます。

使用例については、「 [Operator CDataSource&](#op_cdata_amp) 」を参照してください。

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a> CDataConnection:: operator CSession&amp;

格納されているオブジェクトへの参照を返し `CSession` ます。

### <a name="syntax"></a>構文

```cpp
operator const CSession&();
```

### <a name="remarks"></a>解説

この演算子は、含まれているオブジェクトへの参照を返します。これにより、 `CSession` 参照が必要なオブジェクトを渡すことができ `CDataConnection` `CSession` ます。

### <a name="example"></a>例

参照を受け取る関数 (次のような関数) がある場合は `func` `CSession` 、を使用して `CSession&` オブジェクトを渡すことができ `CDataConnection` ます。

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a> CDataConnection:: operator CSession *

格納されているオブジェクトへのポインターを返し `CSession` ます。

### <a name="syntax"></a>構文

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>解説

この演算子は、含まれているオブジェクトへのポインターを返します。これにより、 `CSession` ポインターが必要なオブジェクトを渡すことができ `CDataConnection` `CSession` ます。

### <a name="example"></a>例

使用例については、「 [Operator CSession&](#op_csession_amp) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
