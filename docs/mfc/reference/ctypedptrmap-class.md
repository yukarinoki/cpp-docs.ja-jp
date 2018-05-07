---
title: CTypedPtrMap クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb0c8679990a48740032017a2c0e11b7148f2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap クラス
ポインター マップ クラス `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`、および `CMapStringToPtr`のオブジェクトに対してタイプ セーフな "ラップ" が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 型付きポインター マップ クラスの基本クラスポインター マップ クラスでなければなりません ( `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`、または`CMapStringToPtr`)。  
  
 `KEY`  
 マップのキーとして使用されるオブジェクトのクラスです。  
  
 `VALUE`  
 マップに格納されているオブジェクトのクラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CTypedPtrMap::Lookup](#lookup)|返します、`KEY`に基づいて、`VALUE`です。|  
|[CTypedPtrMap::RemoveKey](#removekey)|キーで指定された要素を削除します。|  
|[CTypedPtrMap::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrMap::operator](#operator_at)|Map に要素を挿入します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrMap`C++ の型チェック機能は、一致していないポインター型によって発生したエラーを解消します。  
  
 すべて`CTypedPtrMap`関数はインラインでこのテンプレートの使用が大幅には影響しません、コードの速度またはサイズ。  
  
 使用する方法についての`CTypedPtrMap`、記事を参照して[コレクション](../../mfc/collections.md)と[テンプレート ベースのクラス](../../mfc/template-based-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc  
 位置にあるマップ要素を取得`rNextPosition`、し、更新`rNextPosition`をマップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照を指定します、**位置**によって以前返される値`GetNextAssoc`または`BASE_CLASS` **:: 中**呼び出します。  
  
 *KEY*  
 マップのキーの型を指定するテンプレート パラメーター。  
  
 `rKey`  
 取得される要素の返されたキーを指定します。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得される要素の戻り値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、マップ内のすべての要素の反復処理に最も役立ちます。 位置シーケンスがないとは限りませんキーの値のシーケンスと同じに注意してください。  
  
 場合は、取得した最後の要素をマップではの新しい値`rNextPosition`に設定されている**NULL**です。  
  
 このインライン関数が呼び出す`BASE_CLASS` **:: たどる**です。  
  
##  <a name="lookup"></a>  CTypedPtrMap::Lookup  
 `Lookup` ハッシュ アルゴリズムを使用して、すばやく正確に一致するキーを持つマップの要素を検索します。  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 このマップのクラスの基本クラスを指定するテンプレート パラメーター。  
  
 `key`  
 検索する要素のキー。  
  
 *値*  
 このマップに格納されている値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得される要素の戻り値を指定します。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このインライン関数が呼び出す`BASE_CLASS` **:: ルックアップ**です。  
  
##  <a name="operator_at"></a>  CTypedPtrMap::operator  
 この演算子は、代入ステートメント (左辺値) の左側にのみ使用できます。  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>パラメーター  
 *値*  
 このマップに格納されている値の型を指定するテンプレート パラメーター。  
  
 `BASE_CLASS`  
 このマップのクラスの基本クラスを指定するテンプレート パラメーター。  
  
 `key`  
 検索またはマップで作成する要素のキー。  
  
### <a name="remarks"></a>コメント  
 指定されたキーにマップ要素がない場合は、新しい要素が作成されます。 ありません「右側にある」(右辺値) この演算子をキーがマップに見つからない可能性がある可能性があるためです。 使用して、`Lookup`要素を取得します。  
  
##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey  
 このメンバー関数が呼び出す`BASE_CLASS` **:: は**します。  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>パラメーター  
 *KEY*  
 マップのキーの型を指定するテンプレート パラメーター。  
  
 `key`  
 削除する要素のキー。  
  
### <a name="return-value"></a>戻り値  
 項目が見つかり、正常に削除された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)です。  
  
##  <a name="setat"></a>  CTypedPtrMap::SetAt  
 このメンバー関数が呼び出す`BASE_CLASS` **:: SetAt**です。  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *KEY*  
 マップのキーの型を指定するテンプレート パラメーター。  
  
 `key`  
 NewValue のキー値を指定します。  
  
 `newValue`  
 新しい要素の値であるオブジェクトのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)
