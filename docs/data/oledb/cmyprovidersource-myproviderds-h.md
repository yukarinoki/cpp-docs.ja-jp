---
title: CCustomSource (CustomDS.H)
ms.date: 10/22/2018
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
ms.openlocfilehash: 60324ae914c9490144a715e06323ee6d184ce201
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079732"
---
# <a name="ccustomsource-customdsh"></a>CCustomSource (CustomDS .h)

プロバイダークラスは、多重継承を使用します。 次のコードは、データソースオブジェクトの継承チェーンを示しています。

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

すべての COM コンポーネントは、`CComObjectRootEx` と `CComCoClass`から派生します。 `CComObjectRootEx` には、`IUnknown` インターフェイスのすべての実装が用意されています。 すべてのスレッドモデルを処理できます。 `CComCoClass` は、必要なすべてのエラーサポートを処理します。 より充実したエラー情報をクライアントに送信する場合は、`CComCoClass`でエラー Api の一部を使用できます。

データソースオブジェクトは、複数の ' Impl ' クラスからも継承されます。 各クラスは、インターフェイスの実装を提供します。 データソースオブジェクトは、`IPersist`、`IDBProperties`、`IDBInitialize`、および `IDBCreateSession` の各インターフェイスを実装します。 各インターフェイスは、データソースオブジェクトを実装するために OLE DB によって必要になります。 これらのいずれかの ' Impl ' クラスを継承するかどうかによって、特定の機能をサポートするかどうかを選択できます。 `IDBDataSourceAdmin` インターフェイスをサポートする場合は、`IDBDataSourceAdminImpl` クラスから継承して、必要な機能を取得します。

## <a name="com-map"></a>COM マップ

クライアントは、データソースのインターフェイスに対して `QueryInterface` を呼び出すたびに、次の COM マップを経由します。

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

すべての COM コンポーネントは、`CComObjectRootEx` と `CComCoClass`から派生します。 `CComObjectRootEx` には、`IUnknown` インターフェイスのすべての実装が用意されています。 すべてのスレッドモデルを処理できます。 `CComCoClass` は、必要なすべてのエラーサポートを処理します。 より充実したエラー情報をクライアントに送信する場合は、`CComCoClass`でエラー Api の一部を使用できます。

データソースオブジェクトは、複数の ' Impl ' クラスからも継承されます。 各クラスは、インターフェイスの実装を提供します。 データソースオブジェクトは、`IPersist`、`IDBProperties`、`IDBInitialize`、および `IDBCreateSession` の各インターフェイスを実装します。 各インターフェイスは、データソースオブジェクトを実装するために OLE DB によって必要になります。 これらのいずれかの ' Impl ' クラスを継承するかどうかによって、特定の機能をサポートするかどうかを選択できます。 `IDBDataSourceAdmin` インターフェイスをサポートする場合は、`IDBDataSourceAdminImpl` クラスから継承して、必要な機能を取得します。

## <a name="com-map"></a>COM マップ

クライアントは、データソースのインターフェイスに対して `QueryInterface` を呼び出すたびに、次の COM マップを経由します。

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

COM_INTERFACE_ENTRY マクロは ATL からのものであり、適切なインターフェイスを返すために `CComObjectRootEx` で `QueryInterface` の実装を指示します。

## <a name="property-map"></a>プロパティマップ

プロパティマップは、プロバイダーによって割り当てられたすべてのプロパティを指定します。

```cpp
BEGIN_PROPSET_MAP(CCustomSource)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)
      PROPERTY_INFO_ENTRY(CATALOGTERM)
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)
      PROPERTY_INFO_ENTRY(DATASOURCENAME)
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)
      PROPERTY_INFO_ENTRY(DBMSNAME)
      PROPERTY_INFO_ENTRY(DBMSVER)
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)
      PROPERTY_INFO_ENTRY(GROUPBY)
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZE)
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)
      PROPERTY_INFO_ENTRY(NULLCOLLATION)
      PROPERTY_INFO_ENTRY(OLEOBJECTS)
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)
      PROPERTY_INFO_ENTRY(PROCEDURETERM)
      PROPERTY_INFO_ENTRY(PROVIDERNAME)
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)
      PROPERTY_INFO_ENTRY(PROVIDERVER)
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)
      PROPERTY_INFO_ENTRY(SCHEMATERM)
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)
      PROPERTY_INFO_ENTRY(SUBQUERIES)
      PROPERTY_INFO_ENTRY(TABLETERM)
      PROPERTY_INFO_ENTRY(USERNAME)
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)
      PROPERTY_INFO_ENTRY(AUTH_USERID)
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)
      PROPERTY_INFO_ENTRY(INIT_HWND)
      PROPERTY_INFO_ENTRY(INIT_LCID)
      PROPERTY_INFO_ENTRY(INIT_LOCATION)
      PROPERTY_INFO_ENTRY(INIT_MODE)
      PROPERTY_INFO_ENTRY(INIT_PROMPT)
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)
   END_PROPERTY_SET(DBPROPSET_DBINIT)
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)
   CHAIN_PROPERTY_SET(CCustomSession)
END_PROPSET_MAP()
```

OLE DB のプロパティはグループ化されます。 データソースオブジェクトには、2つのプロパティグループがあります。1つは DBPROPSET_DATASOURCEINFO セット用で、もう1つは DBPROPSET_DBINIT セット用です。 DBPROPSET_DATASOURCEINFO セットは、プロバイダーとそのデータソースに関するプロパティに対応しています。 DBPROPSET_DBINIT セットは、初期化時に使用されるプロパティに対応します。 OLE DB プロバイダーテンプレートでは、これらのセットを PROPERTY_SET マクロで処理します。 マクロは、プロパティの配列を含むブロックを作成します。 クライアントが `IDBProperties` インターフェイスを呼び出すたびに、プロバイダーはプロパティマップを使用します。

仕様内のすべてのプロパティを実装する必要はありません。 ただし、必要なプロパティをサポートする必要があります。詳細については、レベル0の準拠の仕様を参照してください。 プロパティをサポートしない場合は、マップから削除できます。 プロパティをサポートする場合は、PROPERTY_INFO_ENTRY マクロを使用して、そのプロパティをマップに追加します。 マクロは、次のコードに示すように、`UPROPINFO` 構造体に対応します。

```cpp
struct UPROPINFO
{
   DBPROPID    dwPropId;
   ULONG       ulIDS;
   VARTYPE     VarType;
   DBPROPFLAGS dwFlags;
   union
   {
      DWORD dwVal;
      LPOLESTR szVal;
   };
   DBPROPOPTIONS dwOption;
};
```

構造体の各要素は、プロパティを処理するための情報を表します。 これには、プロパティの GUID と ID を決定するための `DBPROPID` が含まれています。 また、プロパティの型と値を決定するためのエントリも含まれています。

プロパティの既定値を変更する場合は (コンシューマーが書き込み可能プロパティの値をいつでも変更できることに注意してください)、PROPERTY_INFO_ENTRY_VALUE または PROPERTY_INFO_ENTRY_EX マクロのいずれかを使用できます。 これらのマクロを使用すると、対応するプロパティの値を指定できます。 PROPERTY_INFO_ENTRY_VALUE マクロは、値を変更できる短縮形です。 PROPERTY_INFO_ENTRY_VALUE マクロは、PROPERTY_INFO_ENTRY_EX マクロを呼び出します。 このマクロを使用すると、`UPROPINFO` 構造体のすべての属性を追加または変更できます。

独自のプロパティセットを定義する場合は、追加の BEGIN_PROPSET_MAP/END_PROPSET_MAP の組み合わせを作成することによって追加できます。 プロパティセットの GUID を定義し、独自のプロパティを定義します。 プロバイダー固有のプロパティがある場合は、既存のプロパティを使用するのではなく、新しいプロパティセットに追加します。 これにより、OLE DB の新しいバージョンでの問題を回避できます。

## <a name="user-defined-property-sets"></a>ユーザー定義のプロパティセット

Visual C++は、ユーザー定義のプロパティセットをサポートしています。 `GetProperties` または `GetPropertyInfo`をオーバーライドする必要はありません。 代わりに、テンプレートによって、ユーザー定義のプロパティセットが検出され、適切なオブジェクトに追加されます。

初期化時に使用できるようにする必要があるユーザー定義のプロパティセットがある場合 (つまり、コンシューマーが `IDBInitialize::Initialize`を呼び出す前) は、UPROPSET_USERINIT フラグと BEGIN_PROPERTY_SET_EX マクロを使用して指定できます。 このを機能させるには、プロパティセットがデータソースオブジェクトに含まれている必要があります (OLE DB の仕様に従っている必要があります)。 次に例を示します。

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>参照

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
