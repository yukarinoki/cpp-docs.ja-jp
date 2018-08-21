---
title: IRowsetLocateImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
dev_langs:
- C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0cb4531f1a86d61b72363669d0f722f8dcf204d3
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338390"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl クラス
OLE DB 実装[IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx)インターフェイスで、行セットから任意の行がフェッチされます。  
  
## <a name="syntax"></a>構文

```cpp
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
       T,   
       RowsetInterface,   
       RowClass,   
       MapClass>  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス`IRowsetLocateImpl`します。  
  
 *RowsetInterface*  
 派生したクラス`IRowsetImpl`します。  
  
 *RowClass*  
 記憶域ユニット、`HROW`します。  
  
 *MapClass*  
 プロバイダーによって保持されているすべての行ハンドルのストレージ ユニット。  
  
 *BookmarkKeyType*  
 長整数型や文字列など、ブックマークの型。 通常のブックマークには少なくとも 2 つのバイトの長さが必要です。 (1 バイトの長さは、OLE DB 用に予約された[標準ブックマーク](https://msdn.microsoft.com/library/ms712954.aspx)`DBBMK_FIRST`、 `DBBMK_LAST`、および`DBBMK_INVALID`)。  
  
 *BookmarkType*  
 データへのブックマーク間のリレーションシップを維持するためのマッピング メカニズム。  
  
 *BookmarkMapClass*  
 ブックマークによって保持されているすべての行ハンドルのストレージ ユニット。  

## <a name="requirements"></a>要件  
 **ヘッダー**: atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[Compare](#compare)|2 つのブックマークを比較します。|  
|[GetRowsAt](#getrowsat)|ブックマークからのオフセットで指定した行で始まる行をフェッチします。|  
|[GetRowsByBookmark](#getrowsbybookmark)|指定されたブックマークに一致する行をフェッチします。|  
|[ハッシュ](#hash)|ハッシュの指定されたブックマークの値を返します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_rgBookmarks](#rgbookmarks)|ブックマークの配列。|  
  
## <a name="remarks"></a>Remarks  
 `IRowsetLocateImpl` OLE DB テンプレートの実装、 [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx)インターフェイス。 `IRowsetLocate` 行セットからの任意の行のフェッチに使用されます。 このインターフェイスを実装していない行セットは、`sequential`行セット。 ときに`IRowsetLocate`が存在する、行セット列 0 が行のブックマーク; の同じ行に位置を変更するために使用するブックマークの値を取得はこのコラムを読みます。  
  
 `IRowsetLocateImpl` プロバイダーのブックマーク サポートを実装するために使用されます。 ブックマークは、プレース ホルダー (行セットでのインデックス)、行にすばやく戻るコンシューマーを有効にするデータを高速アクセスを許可します。 プロバイダーは、どのようなブックマークは一意を決定します。 行を識別します。 使用して`IRowsetLocateImpl`メソッド、ブックマークを比較する、行のフェッチがでオフセット、ブックマークによる行のフェッチおよびブックマークのハッシュ値を返します。  
  
 で行セットの OLE DB のブックマークをサポートするには、このクラスから継承する行セットを確認します。  
  
 ブックマークのサポートを実装する方法の詳細については、次を参照してください[プロバイダーのサポートのブックマーク](../../data/oledb/provider-support-for-bookmarks.md)で、 *Visual C++ プログラマ ガイド*と[ブックマーク](https://msdn.microsoft.com/library/ms709728.aspx)、で *。OLE DB プログラマーズ リファレンス*プラットフォーム SDK にします。  

## <a name="compare"></a> Irowsetlocateimpl::compare
2 つのブックマークを比較します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetLocate::Compare](https://msdn.microsoft.com/library/ms709539.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 いずれかのブックマークは、標準 OLE DB 定義[標準ブックマーク](https://msdn.microsoft.com/library/ms712954.aspx)(`DBBMK_FIRST`、 `DBBMK_LAST`、または`DBBMK_INVALID`)。 戻り値`pComparison`2 つのブックマークの間のリレーションシップを示します。  
  
-   DBCOMPARE_LT (`cbBookmark1`前`cbBookmark2`)。  
  
-   DBCOMPARE_EQ (`cbBookmark1`と等しい`cbBookmark2`)。  
  
-   DBCOMPARE_GT (`cbBookmark1`後`cbBookmark2`)。  
  
-   DBCOMPARE_NE (ブックマークは等しいと順序が付いていません)。  
  
-   DBCOMPARE_NOTCOMPARABLE (ブックマークは比較できません。) 

## <a name="getrowsat"></a> Irowsetlocateimpl::getrowsat
ブックマークからのオフセットで指定した行で始まる行をフェッチします。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowsetlocate::getrowsat](https://msdn.microsoft.com/library/ms723031.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 使用する代わりに、カーソル位置からフェッチ、[に](https://msdn.microsoft.com/library/ms723031.aspx)します。  
  
 `IRowsetLocateImpl::GetRowsAt` カーソルの位置は変更されません。 

## <a name="getrowsbybookmark"></a> Irowsetlocateimpl::getrowsbybookmark
指定されたブックマークに一致する 1 つまたは複数の行がフェッチされます。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const DBBKMARK rgcbBookmarks[],  
   const BYTE* rgpBookmarks,  
   HROW rghRows[],  
   DBROWSTATUS* rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する*hChapter*パラメーターを[:getrowsbybookmark](https://msdn.microsoft.com/library/ms725420.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [:getrowsbybookmark](https://msdn.microsoft.com/library/ms725420.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 ブックマークは、定義した値または OLE DB[標準ブックマーク](https://msdn.microsoft.com/library/ms712954.aspx)(`DBBMK_FIRST`または`DBBMK_LAST`)。 カーソルの位置は変更されません。  

## <a name="hash"></a> Irowsetlocateimpl::hash
ハッシュの指定されたブックマークの値を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hReserved*  
 [in]対応する*hChapter*パラメーターを[IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx)します。  
  
 その他のパラメーターでは、次を参照してください。 [IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  

## <a name="rgbookmarks"></a> Irowsetlocateimpl::m_rgbookmarks
ブックマークの配列。  
  
### <a name="syntax"></a>構文  
  
```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;  
```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/library/ms721190.aspx)   
 [プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)   
 [ブックマーク](https://msdn.microsoft.com/library/ms709728.aspx)