---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43c9fdc667f5bd40b6c683f6e48753a084266847
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037649"
---
# <a name="cmapstringtostring-class"></a>メンバー クラス
`CString` オブジェクトをキーとした `CString` オブジェクトのマップをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CMapStringToString`クラスのメンバー関数に似ています[CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md)です。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 任意の場所が表示、`CObject`へのポインターにポインターように、戻り値または"output"関数のパラメーターを置き換える**char**です。 任意の場所が表示、 `CObject` 、「の入力」の関数のパラメーターとしてのポインターへのポインターに置き換える**char**です。  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 たとえば、次のように変換します。  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>パブリック構造体  
  
|name|説明|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|キーの値と関連付けられている文字列オブジェクトの値を含む入れ子になった構造体。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップの要素の数を返します。|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|現在のハッシュ テーブル内の要素数を決定します。|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップの要素の数を返します。|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュ テーブルを初期化します。|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインター キーに基づく void ポインターを検索します。 指す、エンティティではなく、ポインター値は、キーの比較に使用されます。|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定したキー値に関連付けられているキーへの参照を返します。|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|最初のポインターを取得`CString`にマップします。|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|ポインターを取得`CString`の反復処理します。|  
|[CMapStringToString::PLookup](#plookup)|ポインターを返します、`CString`値を持つ指定した値に一致します。|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーで指定された要素を削除します。|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::operator](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Map に要素を挿入などの演算子の代替`SetAt`です。|  
  
## <a name="remarks"></a>Remarks  
 `CMapStringToString` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素がシリアル化されるさらに、アーカイブ、オーバー ロードされた出力ストリームにマップが格納されている場合 ( **<<**) 演算子、または、`Serialize`メンバー関数。  
  
 個別にダンプする必要がある場合`CString` -  `CString`要素、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CMapStringToString`オブジェクトを削除すると、またはその要素が削除されたときに、`CString`オブジェクトは、必要に応じて削除されます。  
  
 詳細については`CMapStringToString`、記事を参照して[コレクション](../../mfc/collections.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="cpair"></a>  CMapStringToString::CPair  
 キー値と関連付けられている文字列オブジェクトの値が含まれています。  
  
### <a name="remarks"></a>Remarks  
 これは、クラス内で入れ子になった構造体[メンバー](../../mfc/reference/cmapstringtostring-class.md)です。  
  
 構造体は、2 つのフィールドで構成されます。  
  
- **キー**キーの型の実際の値。  
  
- **値**関連付けられたオブジェクトの値。  
  
 戻り値の格納に使用されます[CMapStringToString::PLookup](#plookup)、 [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)、および[CMapStringToString::PGetNextAssoc](#pgetnextassoc)です。  
  
### <a name="example"></a>例  
  使用状況の例は、の例を参照してください。 [CMapStringToString::PLookup](#plookup)です。  
  
##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc  
 マップ オブジェクトの最初のエントリを返します。  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>戻り値  
 マップ内の最初のエントリへのポインター参照してください[CMapStringToString::CPair](#cpair)です。 値は、マップが空の場合は、`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 ポインターを返す最初の要素のマップ オブジェクト内には、この関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc  
 によって示されるマップ要素を取得*pAssocRec*です。  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pAssoc*  
 以前によって返されたマップ エントリが指す[PGetNextAssoc](#pgetnextassoc)または[PGetFirstAssoc](#pgetfirstassoc)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次のエントリへのポインター参照してください[CMapStringToString::CPair](#cpair)です。 値は、要素がマップ内の最後の場合は、 **NULL**です。  
  
### <a name="remarks"></a>Remarks  
 マップ内のすべての要素を反復処理するには、このメソッドを呼び出します。 呼び出しの最初の要素を取得`PGetFirstAssoc`を連続する呼び出すと、マップを反復処理し、`PGetNextAssoc`です。  
  
### <a name="example"></a>例  
  例を参照して[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)です。  
  
##  <a name="plookup"></a>  CMapStringToString::PLookup  
 指定されたキーにマップされている値を検索します。  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 検索する要素のキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたキーへのポインター。  
  
### <a name="remarks"></a>Remarks  
 指定したキーと一致するキーを使用して、マップ要素を検索するには、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



