---
title: CAnimationSize クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1002ace78cf58c34c5e89bbafd81460ec5dabc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354136"
---
# <a name="canimationsize-class"></a>CAnimationSize クラス
サイズをアニメーション化できるサイズ オブジェクトの機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|オーバーロードされます。 アニメーション サイズ オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|幅と高さの遷移を追加します。|  
|[CAnimationSize::GetCX](#getcx)|幅を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationSize::GetCY](#getcy)|高さを表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|既定値の幅と高さを返します。|  
|[CAnimationSize::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|CSize、CAnimationSize に変換します。|  
|[CAnimationSize::operator =](#operator_eq)|CAnimationSize に szSrc を割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|アニメーションのサイズの幅を表すアニメーションをカプセル化された変数です。|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|アニメーションのサイズの高さを表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationSize クラスは、2 つの CAnimationVariable オブジェクトをカプセル化し、サイズのアプリケーションで表すことができます。 任意の 2 つのサイズをアニメーション化するこのクラスを使用するなど、画面上の次元のオブジェクト (四角形のような制御など)。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加してだけの幅または高さに適用される各移行につき AddTransition を呼び出すです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationSize::AddTransition  
 幅と高さの遷移を追加します。  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCXTransition`  
 幅の遷移へのポインター。  
  
 `pCYTransition`  
 高さの遷移へのポインター。  
  
### <a name="remarks"></a>コメント  
 変数に適用するアニメーションの幅と高さへの遷移の内部リストに指定された遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり、内部の一覧に格納されています。 遷移を (特定の値のストーリー ボードへの追加) に適用されます CAnimationController::AnimateGroup を呼び出すとします。 ディメンションの 1 つの遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="canimationsize"></a>  CAnimationSize::CAnimationSize  
 アニメーション サイズ オブジェクトを構築します。  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `szDefault`  
 既定のサイズを指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 幅、高さの既定値を持つオブジェクトが構築されたオブジェクトの ID とグループの ID を 0 に設定されます。 これらは、SetDefaultValue および SetID を使用して実行時に後で変更することができます。  
  
##  <a name="getanimationvariablelist"></a>  CAnimationSize::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、幅と高さを表す 2 つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="getcx"></a>  CAnimationSize::GetCX  
 幅を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>戻り値  
 幅を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 幅を表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getcy"></a>  CAnimationSize::GetCY  
 高さを表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>戻り値  
 高さを表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 高さを表す、基になる CAnimationVariable に直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="getdefaultvalue"></a>  CAnimationSize::GetDefaultValue  
 既定値の幅と高さを返します。  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 既定値を含む CSize オブジェクト。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="getvalue"></a>  CAnimationSize::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `szValue`  
 出力です。 このメソッドが戻るとき、現在の値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーションのサイズの現在の値を取得するには、この関数を呼び出します。 このメソッドが失敗した、または幅とサイズを基になる COM オブジェクトが初期化されていない、szValue には、コンス トラクターまたは SetDefaultValue によって設定されている既定値が含まれています。  
  
##  <a name="m_cxvalue"></a>  CAnimationSize::m_cxValue  
 アニメーションのサイズの幅を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>  CAnimationSize::m_cyValue  
 アニメーションのサイズの高さを表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>  CAnimationSize::operator CSize  
 CSize、CAnimationSize に変換します。  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>戻り値  
 CSize とサイズをアニメーションの現在の値。  
  
### <a name="remarks"></a>コメント  
 この関数は、GetValue を内部的に呼び出します。 GetValue 何らかの理由により失敗した場合、返されるサイズは幅と高さの既定値が格納されます。  
  
##  <a name="operator_eq"></a>  CAnimationSize::operator =  
 CAnimationSize に szSrc を割り当てます。  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `szSrc`  
 CSize またはサイズを指します。  
  
### <a name="remarks"></a>コメント  
 CAnimationSize に szSrc を割り当てます。 お勧めをアニメーションの開始前に行うにはこの演算子は、それが作成された場合に、幅と高さの基になる COM オブジェクトを作成し直さ SetDefaultValue を呼び出すためです。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>  CAnimationSize::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `szDefault`  
 新しい既定のサイズを指定します。  
  
### <a name="remarks"></a>コメント  
 既定値をアニメーション オブジェクトに設定するのにには、この関数を使用します。 このメソッドは、既定値をアニメーションのサイズの幅と高さに割り当てます。 それが作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
