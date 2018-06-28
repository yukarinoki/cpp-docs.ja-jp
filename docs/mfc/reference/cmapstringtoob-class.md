---
title: CMapStringToOb クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
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
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
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
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4ea4ea24dfae26b1b43fe6480cac7f7a480fa4
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042249"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb クラス
一意の `CString` オブジェクトを `CObject` へのポインターに割り当てる辞書コレクション クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|このマップの要素の数を返します。|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|現在のハッシュ テーブル内の要素数を決定します。|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMapStringToOb::GetSize](#getsize)|このマップの要素の数を返します。|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|最初の要素の位置を返します。|  
|[CMapStringToOb::HashKey](#hashkey)|指定したキーのハッシュ値を計算します。|  
|[CMapStringToOb::InitHashTable](#inithashtable)|ハッシュ テーブルを初期化します。|  
|[CMapStringToOb::IsEmpty](#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMapStringToOb::Lookup](#lookup)|Void ポインター キーに基づく void ポインターを検索します。 指す、エンティティではなく、ポインター値は、キーの比較に使用されます。|  
|[CMapStringToOb::LookupKey](#lookupkey)|指定したキー値に関連付けられているキーへの参照を返します。|  
|[CMapStringToOb::RemoveAll](#removeall)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](#removekey)|キーで指定された要素を削除します。|  
|[CMapStringToOb::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::operator](#operator_at)|Map に要素を挿入などの演算子の代替`SetAt`です。|  
  
## <a name="remarks"></a>Remarks  
 挿入すると、 `CString` -  `CObject*`ペア (要素) に、マップには、効率的に取得したり、文字列を使用してペアリングが削除することができます、または`CString`キーと値。 マップ内のすべての要素を繰り返すこともできます。  
  
 型の変数**位置**すべての種類のマップ内の別のエントリのアクセスに使用します。 使用することができます、**位置**「に注意してください」のエントリをマップを反復処理します。 このイテレーションが順のキー値であると思われる場合があります。そうじゃないです。 取得された要素の順序が不定になります。  
  
 `CMapStringToOb` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素がシリアル化されるさらに、アーカイブ、オーバー ロードされた出力ストリームにマップが格納されている場合 ( **<<**) 演算子、または、`Serialize`メンバー関数。  
  
 マップ内の個々 の要素の診断ダンプが必要なかどうか (、`CString`値、および`CObject`内容)、ダンプ コンテキストの深さは 1 以上を設定する必要があります。  
  
 ときに、`CMapStringToOb`オブジェクトを削除すると、またはその要素が削除されたときに、`CString`オブジェクトおよび`CObject`ポインターを削除します。 によって参照されるオブジェクト、`CObject`ポインターは破棄されません。  
  
 マップ クラスの派生は、リストの派生に似ています。 記事を参照して[コレクション](../../mfc/collections.md)特別な用途の一覧のクラスの派生の詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>  CMapStringToOb::CMapStringToOb  
 空の構築`CString`対`CObject*`マップします。  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBlockSize*  
 マップを拡張するためのメモリ割り当ての粒度を指定します。  
  
### <a name="remarks"></a>Remarks  
 単位でメモリが割り当てられているマップするにつれて、 *nBlockSize*エントリです。  
  
 次の表はその他のメンバー関数に似ています**CMapStringToOb:: CMapStringToOb**です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb( INT_PTR** `nBlockSize` **= 10 );**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr( INT_PTR** `nBlockSize` **= 10 );**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
##  <a name="getcount"></a>  CMapStringToOb::GetCount  
 マップの要素の数が決まります。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップ内の要素の数。  
  
### <a name="remarks"></a>Remarks  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::GetCount`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>  CMapStringToOb::GetHashTableSize  
 現在のハッシュ テーブル内の要素数を決定します。  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブル内の要素の数を返します。  
  
### <a name="remarks"></a>Remarks  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::GetHashTableSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; UINT GetHashTableSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; UINT GetHashTableSize)**|  
  
##  <a name="getnextassoc"></a>  CMapStringToOb::GetNextAssoc  
 位置にあるマップ要素を取得*rNextPosition*、し、更新*rNextPosition*をマップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rNextPosition*  
 参照を指定します、**位置**によって以前返される値**たどる**または**中**呼び出します。  
  
 *rKey*  
 取得された要素 (文字列) の返されたキーを指定します。  
  
 *rValue*  
 取得される要素の戻り値を指定します (、 **CObject**ポインター)。 このパラメーターの詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>Remarks  
 この関数は、マップ内のすべての要素の反復処理に最も役立ちます。 位置シーケンスがないとは限りませんキーの値のシーケンスと同じに注意してください。  
  
 場合は、取得した最後の要素をマップではの新しい値*rNextPosition*に設定されている**NULL**です。  
  
 *右辺値*パラメーターに、オブジェクト型にキャストすることを確認する**CObject\*&**、これは、コンパイラは、次の例に示すように。  
  
 [!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 これには当てはまりません**たどる**テンプレートを基にマップします。  
  
 次の表はその他のメンバー関数に似ています**CMapStringToOb::GetNextAssoc**です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, void\*&** *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, WORD&** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, CString&** *rKey* **, void\*&** *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, CString&** *rKey* **, CString&** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, WORD&** *rKey* **, CObject\*&** *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, WORD&** *rKey* **, void\*&** *rValue* **) const;**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>  CMapStringToOb::GetSize  
 マップ要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内のアイテムの数。  
  
### <a name="remarks"></a>Remarks  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::GetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>  CMapStringToOb::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextAssoc`呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>Remarks  
 イテレーションのシーケンスが予測可能です。したがって、マップの最初の要素""には、特別な意味はありません。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::GetStartPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition( ) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition( ) const;**|  
  
### <a name="example"></a>例  
 例を参照して[CMapStringToOb::GetNextAssoc](#getnextassoc)です。  
  
##  <a name="hashkey"></a>  CMapStringToOb::HashKey  
 指定したキーのハッシュ値を計算します。  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 ハッシュ値が計算されるキー。  
  
### <a name="return-value"></a>戻り値  
 キーのハッシュ値  
  
### <a name="remarks"></a>Remarks  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::HashKey`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\***  `key` **) const です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\***  `key` **) const です。**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const です。**|  
  
##  <a name="inithashtable"></a>  CMapStringToOb::InitHashTable  
 ハッシュ テーブルを初期化します。  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *hashSize*  
 ハッシュ テーブル内のエントリの数です。  
  
 *bAllocNow*  
 場合**TRUE**初期化時にハッシュ テーブルを割り当てる必要なときにそれ以外の場合、テーブルが割り当てられます。  
  
### <a name="remarks"></a>Remarks  
 最適なパフォーマンスをハッシュ テーブルのサイズは、素数をする必要があります。 競合を最小限に抑えるには、サイズする必要があります約 20%、最大の予想されるデータ セットよりも大きいです。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::InitHashTable`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE );**|  
  
##  <a name="isempty"></a>  CMapStringToOb::IsEmpty  
 マップが空かどうかを判断します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップに要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 例を参照して[RemoveAll](#removeall)です。  
  
### <a name="remarks"></a>Remarks  
 次の表はその他のメンバー関数に似ています**CMapStringToOb:: IsEmpty**です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; BOOL IsEmpty)**|  
  
##  <a name="lookup"></a>  CMapStringToOb::Lookup  
 返します、`CObject`ポインターがに基づいて、`CString`値。  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 検索する要素を識別する文字列のキーを指定します。  
  
 *rValue*  
 検索された要素から返された値を指定します。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `Lookup` ハッシュ アルゴリズムを使用してすばやく正確に一致するキーを持つマップの要素を検索 (`CString`値)。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::LookUp`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL ルックアップ (void\***  `key` **, void\* &**  `rValue` **) const です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL ルックアップ (void\***  `key` **、WORD &** `rValue` **) const です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL ルックアップ (LPCTSTR** `key` **, void\* &**  `rValue` **) const です。**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL ルックアップ (LPCTSTR** `key` **、CString &** `rValue` **) const です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL ルックアップ (WORD** `key` **、CObject\* &**  `rValue` **) const です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL ルックアップ (WORD** `key` **, void\* &**  `rValue` **) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>  CMapStringToOb::LookupKey  
 指定したキー値に関連付けられているキーへの参照を返します。  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 検索する要素を識別する文字列のキーを指定します。  
  
 *rKey*  
 関連付けられているキーへの参照。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 関連付けられている要素がマップから削除された後に使用する場合、またはマップの破棄された後は、キーへの参照を使用しても安全です。  
  
 次の表はその他のメンバー関数に似ています**CMapStringToOb:: LookupKey**です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **、lpctstr を使用する (& a)** `rKey` **) const です。**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **、lpctstr を使用する (& a)** `rKey` **) const です。**|  
  
##  <a name="operator_at"></a>  CMapStringToOb::operator [ ]  
 便利な代替には、`SetAt`メンバー関数。  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターへの参照、`CObject`オブジェクトまたは**NULL**マップが空の場合または*キー*が範囲外です。  
  
### <a name="remarks"></a>Remarks  
 したがって、代入ステートメント (左辺値) の左側にのみ使用できます。 指定されたキーにマップ要素がない場合は、新しい要素が作成されます。  
  
 ありません「右側にある」(右辺値) この演算子をキーがマップに見つからない可能性がある可能性があるためです。 使用して、`Lookup`要素を取得します。  
  
 次の表はその他のメンバー関数に似ています**CMapStringToOb::operator:operator[]** です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& operator[](void\*** `key` **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD& operator[](void\*** `key` **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator[](lpctstr** `key` **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString& operator[](lpctstr** `key` **\);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& 演算子 (word** `key` **\)です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator[](word** `key` **\);**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>  CMapStringToOb::RemoveAll  
 このマップからすべての要素を削除し、破棄、 `CString` key オブジェクトです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarks  
 `CObject`各キーによって参照されるオブジェクトは破棄されません。 `RemoveAll`するは保証されませんを参照されている場合、関数はメモリ リークを起こすことができます`CObject`オブジェクトは破棄されます。  
  
 関数は、マップがまだ空の場合、正常に動作します。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::RemoveAll`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll( );**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll( );**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll( );**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll( );**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll( );**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>  CMapStringToOb::RemoveKey  
 指定されたキーに対応するマップ エントリを検索します。次に、キーが見つかった場合は、エントリを削除します。  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 マップの検索に使用する文字列を指定します。  
  
### <a name="return-value"></a>戻り値  
 項目が見つかり、正常に削除された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 これは、場合にメモリ リークを発生できます、`CObject`オブジェクトは他の場所に削除されません。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::RemoveKey`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**ブール値には (void\***  `key` **) です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**ブール値には (void\***  `key` **) です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブール値には (LPCTSTR** `key` **) です。**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**ブール値には (LPCTSTR** `key` **) です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**ブール値には (WORD** `key` **) です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**ブール値には (WORD** `key` **) です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>  CMapStringToOb::SetAt  
 プライマリは、マップの要素を挿入することを意味します。  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *key*  
 新しい要素のキーである文字列を指定します。  
  
 *newValue*  
 指定します、`CObject`新しい要素の値を示すポインターです。  
  
### <a name="remarks"></a>Remarks  
 最初に、キーが検索されます。 キーが見つかった場合、対応する値を変更するとします。それ以外の場合、新しいキーと値の要素が作成されます。  
  
 次の表はその他のメンバー関数に似ています`CMapStringToOb::SetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void\*** `key` **, void\*** `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt( void\*** `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void\*** `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**SetAt を無効にする (WORD** `key` **、CObject\***  `newValue` **) です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt( WORD** `key` **, void\*** `newValue` **);**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)   
 [メンバー クラス](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb クラス](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)
