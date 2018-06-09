---
title: CMap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89e508242e7318e5419656720b6dee20bed55716
ms.sourcegitcommit: 59afc95d0e494af658cf464503f7f89bd1a8d2ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "35239425"
---
# <a name="cmap-class"></a>CMap クラス
一意なキーを値に割り当てる辞書コレクション クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>パラメーター  
 `KEY`  
 マップのキーとして使用されるオブジェクトのクラスです。  
  
 `ARG_KEY`  
 データ型`KEY`引数です。 通常はへの参照を`KEY`です。  
  
 `VALUE`  
 マップに格納されているオブジェクトのクラスです。  
  
 `ARG_VALUE`  
 データ型`VALUE`引数です。 通常はへの参照を`VALUE`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-structures"></a>パブリック構造体  
  
|name|説明|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|キーの値と、関連オブジェクトの値を含む入れ子になった構造体。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|値をキーにマップするコレクションを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|このマップの要素の数を返します。|  
|[CMap::GetHashTableSize](#gethashtablesize)|ハッシュ テーブル内の要素の数を返します。|  
|[CMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMap::GetSize](#getsize)|このマップの要素の数を返します。|  
|[CMap::GetStartPosition](#getstartposition)|最初の要素の位置を返します。|  
|[CMap::InitHashTable](#inithashtable)|ハッシュ テーブルを初期化し、そのサイズを指定します。|  
|[CMap::IsEmpty](#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMap::Lookup](#lookup)|指定されたキーにマップされている値を検索します。|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|最初の要素へのポインターを返します。|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|繰り返し処理で次の要素へのポインターを取得します。|  
|[例](#plookup)|値が指定の値に一致するキーへのポインターを返します。|  
|[CMap::RemoveAll](#removeall)|このマップからすべての要素を削除します。|  
|[CMap::RemoveKey](#removekey)|キーで指定された要素を削除します。|  
|[CMap::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::operator](#operator_at)|Map に要素を挿入などの演算子の代替`SetAt`です。|  
  
## <a name="remarks"></a>Remarks  
 マップにキー/値ペア (要素) を挿入すると効率的に取得したりへのアクセス キーを使用してペアリングが削除することができます。 マップ内のすべての要素を繰り返すこともできます。  
  
 型の変数**位置**エントリに代替のアクセスに使用します。 使用することができます、**位置**「に注意してください」のエントリをマップを反復処理します。 このイテレーションが順のキー値であると思われる場合があります。そうじゃないです。 取得された要素の順序が不定になります。  
  
 ほとんどの用途のグローバルのヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CMap`クラスです。 参照してください[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)のマクロとグローバルのセクションで、`MFC Reference`です。  
  
 `CMap` オーバーライド[cobject::serialize](../../mfc/reference/cobject-class.md#serialize)シリアル化とその要素のダンプをサポートするためにします。 使用して、アーカイブするマップが格納されている場合`Serialize`、各マップ要素がさらにシリアル化します。 既定の実装、`SerializeElements`ヘルパー関数ではビットごとの書き込み。 派生したポインター コレクション アイテムのシリアル化に関する情報の`CObject`またはその他のユーザー定義型を参照してください[する方法: タイプ セーフなコレクションを作成する](../../mfc/how-to-make-a-type-safe-collection.md)です。  
  
 (キーと値) のマップ内の個々 の要素の診断ダンプする場合は、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CMap`オブジェクトを削除すると、またはその要素が削除された場合、キーと値の両方が削除されます。  
  
 マップ クラスの派生は、リストの派生に似ています。 記事を参照して[コレクション](../../mfc/collections.md)特別な用途の一覧のクラスの派生の詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="cmap"></a>  CMap::CMap  
 空のマップを構築します。  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 マップを拡張するためのメモリ割り当ての粒度を指定します。  
  
### <a name="remarks"></a>Remarks  
 単位でメモリが割り当てられているマップするにつれて、`nBlockSize`エントリです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>  CMap::CPair  
 キー値と関連付けられたオブジェクトの値が含まれています。  
  
### <a name="remarks"></a>Remarks  
 これは、クラス内で入れ子になった構造体[CMap](../../mfc/reference/cmap-class.md)です。  
  
 構造体は、2 つのフィールドで構成されます。  
  
- **キー**キーの型の実際の値。  
  
- **値**関連付けられたオブジェクトの値。  
  
 戻り値の格納に使用されます[例](#plookup)、 [CMap::PGetFirstAssoc](#pgetfirstassoc)、および[CMap::PGetNextAssoc](#pgetnextassoc)です。  
  
### <a name="example"></a>例  
 使用状況の例は、の例を参照してください。[例](#plookup)です。  
  
##  <a name="getcount"></a>  CMap::GetCount  
 マップ内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数。  
  
### <a name="example"></a>例  
 例を参照して[CMap::Lookup](#lookup)です。  
  
##  <a name="gethashtablesize"></a>  CMap::GetHashTableSize  
 マップのハッシュ テーブル内の要素の数を決定します。  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブル内の要素の数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>  CMap::GetNextAssoc  
 位置にあるマップ要素を取得`rNextPosition`、し、更新`rNextPosition`をマップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rNextPosition`  
 参照を指定します、**位置**によって以前返される値`GetNextAssoc`または`GetStartPosition`呼び出します。  
  
 *KEY*  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 `rKey`  
 取得される要素の返されたキーを指定します。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得される要素の戻り値を指定します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、マップ内のすべての要素の反復処理に最も役立ちます。 位置シーケンスがないとは限りませんキーの値のシーケンスと同じに注意してください。  
  
 場合は、取得した最後の要素をマップではの新しい値`rNextPosition`に設定されている**NULL**です。  
  
### <a name="example"></a>例  
 例を参照して[CMap::SetAt](#setat)です。  
  
##  <a name="getsize"></a>  CMap::GetSize  
 マップ要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内のアイテムの数。  
  
### <a name="remarks"></a>Remarks  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>  CMap::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextAssoc`呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>Remarks  
 イテレーションのシーケンスが予測可能です。したがって、マップの最初の要素""には、特別な意味はありません。  
  
### <a name="example"></a>例  
 例を参照して[CMap::SetAt](#setat)です。  
  
##  <a name="inithashtable"></a>  CMap::InitHashTable  
 ハッシュ テーブルを初期化します。  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hashSize`  
 ハッシュ テーブル内のエントリの数です。  
  
 `bAllocNow`  
 場合**TRUE**初期化時にハッシュ テーブルを割り当てる必要なときにそれ以外の場合、テーブルが割り当てられます。  
  
### <a name="remarks"></a>Remarks  
 最適なパフォーマンスをハッシュ テーブルのサイズは、素数をする必要があります。 競合を最小限に抑えるには、サイズする必要があります約 20%、最大の予想されるデータ セットよりも大きいです。  
  
### <a name="example"></a>例  
 例を参照して[CMap::Lookup](#lookup)です。  
  
##  <a name="isempty"></a>  CMap::IsEmpty  
 マップが空かどうかを判断します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップに要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 例を参照して[CMap::RemoveAll](#removeall)です。  
  
##  <a name="lookup"></a>  CMap::Lookup  
 指定されたキーにマップされている値を検索します。  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 テンプレート パラメーターの型を指定する、`key`値。  
  
 `key`  
 検索する要素を識別するキーを指定します。  
  
 *値*  
 検索する値の型を指定します。  
  
 `rValue`  
 検索された値を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `Lookup` ハッシュ アルゴリズムを使用して、指定したキーと一致するキーを持つマップの要素をすばやく検索します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>  CMap::operator  
 便利な代替には、`SetAt`メンバー関数。  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>パラメーター  
 *値*  
 マップ値の型を指定するテンプレート パラメーター。  
  
 `ARG_KEY`  
 キーの値の型を指定するテンプレート パラメーター。  
  
 `key`  
 マップの値を取得するために使用するキー。  
  
### <a name="remarks"></a>Remarks  
 したがって、代入ステートメント (左辺値) の左側にのみ使用できます。 指定されたキーにマップ要素がない場合は、新しい要素が作成されます。  
  
 ありません「右側にある」(右辺値) この演算子をキーがマップに見つからない可能性がある可能性があるためです。 使用して、`Lookup`要素を取得します。  
  
### <a name="example"></a>例  
 例を参照して[CMap::Lookup](#lookup)です。  
  
##  <a name="pgetfirstassoc"></a>  CMap::PGetFirstAssoc  
 マップ オブジェクトの最初のエントリを返します。  
  
```  
const CPair* PGetFirstAssoc() const; 
CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内の最初のエントリへのポインター参照してください[CMap::CPair](#cpair)です。 マップにエントリが含まれていない場合、値は**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 ポインターを返す最初の要素のマップ オブジェクト内には、この関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>  CMap::PGetNextAssoc  
 によって示されるマップ要素を取得`pAssocRec`です。  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>パラメーター  
 *pAssocRet*  
 以前によって返されたマップ エントリが指す[PGetNextAssoc](#pgetnextassoc)または[CMap::PGetFirstAssoc](#pgetfirstassoc)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次のエントリへのポインター参照してください[CMap::CPair](#cpair)です。 値は、要素がマップ内の最後の場合は、 **NULL**です。  
  
### <a name="remarks"></a>Remarks  
 マップ内のすべての要素を反復処理するには、このメソッドを呼び出します。 呼び出しの最初の要素を取得`PGetFirstAssoc`を連続する呼び出すと、マップを反復処理し、`PGetNextAssoc`です。  
  
### <a name="example"></a>例  
 例を参照して[CMap::PGetFirstAssoc](#pgetfirstassoc)です。  
  
##  <a name="plookup"></a>  例  
 指定されたキーにマップされている値を検索します。  
  
```  
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素のキー。  
  
### <a name="return-value"></a>戻り値  
 キーの構造体へのポインター参照してください[CMap::CPair](#cpair)です。 一致するものが見つからない場合`CMap::PLookup`返します`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 指定したキーと一致するキーを使用して、マップ要素を検索するには、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 グローバルなヘルパー関数を呼び出すことによって、このマップからすべての値を削除**DestructElements**です。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarks  
 関数は、マップがまだ空の場合、正常に動作します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 指定されたキーに対応するマップ エントリを検索します。次に、キーが見つかった場合は、エントリを削除します。  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 キーの型を指定するテンプレート パラメーター。  
  
 `key`  
 削除する要素のキー。  
  
### <a name="return-value"></a>戻り値  
 項目が見つかり、正常に削除された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 **DestructElements**ヘルパー関数を使用して、エントリを削除します。  
  
### <a name="example"></a>例  
 例を参照して[CMap::SetAt](#setat)です。  
  
##  <a name="setat"></a>  CMap::SetAt  
 プライマリは、マップの要素を挿入することを意味します。  
  
```  
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 テンプレート パラメーターの型を指定する、`key`パラメーター。  
  
 `key`  
 新しい要素のキーを指定します。  
  
 `ARG_VALUE`  
 テンプレート パラメーターの型を指定する、`newValue`パラメーター。  
  
 `newValue`  
 新しい要素の値を指定します。  
  
### <a name="remarks"></a>Remarks  
 最初に、キーが検索されます。 キーが見つかった場合、対応する値を変更するとします。それ以外の場合、新しいキー値のペアが作成されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)  
