---
title: CMyProviderSource (MyProviderDS.H) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- myproviderds.h
- cmyprovidersource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f141ad7565a78ff4e7a02b3847287879b81ccd6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource (MyProviderDS.H)
プロバイダー クラスは、複数の継承を使用します。 次のコードは、データ ソース オブジェクトの継承チェーンを示しています。  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 すべての COM コンポーネントから派生して`CComObjectRootEx`と`CComCoClass`です。 `CComObjectRootEx` すべての実装を提供、 **IUnknown**インターフェイスです。 すべてのスレッド モデルを処理できます。 `CComCoClass` 必要なすべてのエラー サポートを処理します。 詳細なエラー情報をクライアントに送信する場合は、Api のエラーの一部を使用で`CComCoClass`です。  
  
 データ ソース オブジェクトは、'Impl' クラスがいくつかからも継承します。 各クラスは、インターフェイスの実装を提供します。 データ ソース オブジェクトを実装して、 `IPersist`、 `IDBProperties`、 **IDBInitialize**、および**IDBCreateSession**インターフェイスです。 各インターフェイスには、データ ソース オブジェクトを実装する OLE DB が必要です。 サポートしたり、継承、またはそのいずれかのこれら 'Impl' クラスから継承せず、特定の機能をサポートしないことができます。 サポートする場合、 **IDBDataSourceAdmin**から継承するインターフェイスを**IDBDataSourceAdminImpl**のために必要な機能を実装するクラス。  
  
## <a name="com-map"></a>COM マップ  
 クライアントが呼び出すたびに`QueryInterface`インターフェイスについては、データ ソースで、次の COM マップを介してなります。  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 COM_INTERFACE_ENTRY マクロと通知の実装は ATL からが`QueryInterface`で`CComObjectRootEx`を適切なインターフェイスを返します。  
  
## <a name="property-map"></a>プロパティ マップ  
 プロパティ マップは、プロバイダーによって指定されたすべてのプロパティを指定します。  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
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
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 OLE db プロパティがグループ化されます。 データ ソース オブジェクトがプロパティの 2 つのグループを持つ: のいずれか、 **DBPROPSET_DATASOURCEINFO**セットから 1 つずつ、 **DBPROPSET_DBINIT**を設定します。 **DBPROPSET_DATASOURCEINFO**セットは、プロバイダーとそのデータ ソースのプロパティに対応しています。 **DBPROPSET_DBINIT**セットが初期化に使用されるプロパティに対応しています。 OLE DB プロバイダー テンプレートは、PROPERTY_SET マクロでこれらのセットを処理します。 マクロは、プロパティの配列を格納するブロックを作成します。 クライアントが呼び出すたびに、`IDBProperties`インターフェイス、プロバイダーは、プロパティ マップを使用します。  
  
 仕様のすべてのプロパティを実装する必要はありません。 ただし、必要なプロパティをサポートする必要があります。詳細については、レベル 0 への準拠の仕様を参照してください。 プロパティをサポートしない場合は、マップから削除できます。 プロパティをサポートする場合は、追加、マップに PROPERTY_INFO_ENTRY マクロを使用しています。 マクロに対応する、 **UPROPINFO**次のコードに示すように構造体します。  
  
```  
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
  
 構造内の各要素は、プロパティを処理する情報を表します。 含まれている、 **DBPROPID**プロパティの GUID と ID を指定します。 型とプロパティの値を特定のエントリも含まれています。  
  
 プロパティ (コンシューマーがいつでも書き込み可能なプロパティの値を変更ことに注意してください) の既定値を変更する場合は、PROPERTY_INFO_ENTRY_VALUE または PROPERTY_INFO_ENTRY_EX マクロを使用することができます。 これらのマクロを使用すると、対応するプロパティの値を指定できます。 PROPERTY_INFO_ENTRY_VALUE マクロは、値を変更することができます略式の表記です。 PROPERTY_INFO_ENTRY_VALUE マクロは、PROPERTY_INFO_ENTRY_EX マクロを呼び出します。 このマクロでは、すべての属性の変更を追加することができます、 **UPROPINFO**構造体。  
  
 独自のプロパティ セットを定義する場合は、追加の BEGIN_PROPSET_MAP/END_PROPSET_MAP 組み合わせにすることで 1 つを追加できます。 プロパティ セットの GUID を定義し、独自のプロパティを定義する必要があります。 プロバイダー固有のプロパティがあれば、既存のものを使用する代わりに設定された新しいプロパティに追加します。 以降のバージョンの OLE DB での問題を回避できます。  
  
## <a name="user-defined-property-sets"></a>ユーザー定義のプロパティ セット  
 Visual C には、ユーザー定義のプロパティ セットがサポートしています。 オーバーライドする必要はありません**GetProperties**または`GetPropertyInfo`です。 代わりに、テンプレートは、任意のユーザー定義のプロパティ セットを検出し、適切なオブジェクトに追加します。  
  
 初期化時に使用する必要があるユーザー定義のプロパティ セットがある場合 (コンシューマーを呼び出す前に、 **idbinitialize::initialize**) を使用してこれを指定することができます、 **UPROPSET_USERINIT** BEGIN_PROPERTY_SET_EX マクロと組み合わせてフラグ。 プロパティ セットは、これは、OLE DB 仕様が必要です) のデータ ソース オブジェクトでなければなりません。 例えば:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>関連項目  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)