---
title: CBaseKeyFrame クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3de348131dded63794e818d40c0ac5aeae910b03
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956709"
---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame クラス
キーフレームの基本機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|キーフレームのオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|ストーリー ボードにキーフレームを追加します。|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|キーフレームの基になる値を返します。|  
|[CBaseKeyFrame::IsAdded](#isadded)|ストーリー ボードにキーフレームが追加されているかどうかを指示します。|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|ストーリー ボードのオフセット、または移行後に、キーフレームを追加するかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|このキーフレームがストーリー ボードに追加されたかどうかを指定します。|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|このキーフレームをストーリー ボードの別の既存のキーフレームからのオフセットまたはいくつかの遷移の末尾に追加するかどうかを指定します。|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Windows Animation API キーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START 定義済みの値に設定されます。|  
  
## <a name="remarks"></a>Remarks  
 UI_ANIMATION_KEYFRAME 変数をカプセル化します。 任意のキーフレームの実装の基本クラスとして機能します。 キーフレームは、ストーリー ボード内の特定の時点を表し、遷移の開始と終了時刻を指定するために使用できます。 キーフレームのキーフレーム (世界時刻)、指定したオフセットでストーリー ボードに追加または指定された移行後に、追加のキーフレームの 2 種類があります。 アニメーションの開始前に一部の切り替え効果の期間を特定できないために、実行時のみにいくつかのキーフレームの実際の値が決定されます。 キーフレームを順番にキーフレームに依存している遷移に依存するため、キーフレーム チェーンを構築するときに、無限再帰を防ぐ必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CBaseKeyFrame::AddToStoryboard  
 ストーリー ボードにキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStoryboard*  
 ストーリー ボードへのポインター。  
  
 *bDeepAdd*  
 このパラメーターが TRUE であり、追加するキーフレームがいくつか他のキーフレームや遷移に依存する場合、このメソッドはこのキーフレームまたは最初にストーリー ボードへの移行を追加しようとします。  
  
### <a name="return-value"></a>戻り値  
 キーフレームが正常にストーリー ボードに追加された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 ストーリー ボードにキーフレームを追加する、このメソッドが呼び出されます。  
  
##  <a name="cbasekeyframe"></a>  CBaseKeyFrame::CBaseKeyFrame  
 キーフレームのオブジェクトを構築します。  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>  CBaseKeyFrame::GetAnimationKeyframe  
 キーフレームの基になる値を返します。  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のキーフレームです。 既定値は、UI_ANIMATION_KEYFRAME_STORYBOARD_START です。  
  
### <a name="remarks"></a>Remarks  
 これは、アクセサーを基になるキーフレーム値です。  
  
##  <a name="isadded"></a>  CBaseKeyFrame::IsAdded  
 ストーリー ボードにキーフレームが追加されているかどうかを指示します。  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードにキーフレームを追加する場合は TRUE。そう FALSE。  
  
### <a name="remarks"></a>Remarks  
 基底クラスでも常に TRUE を返しますが、派生クラスでオーバーライドされます。  
  
##  <a name="iskeyframeatoffset"></a>  CBaseKeyFrame::IsKeyframeAtOffset  
 ストーリー ボードのオフセット、または移行後に、キーフレームを追加するかどうかを指定します。  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ストーリー ボードのいくつかの指定したオフセット位置にキーフレームを追加する必要があります。 FALSE の場合、いくつかの移行が完了した後ストーリー ボードにキーフレームを追加する必要があります。  
  
### <a name="remarks"></a>Remarks  
 ストーリー ボードのオフセット位置にキーフレームを追加する必要があるかどうかを指定します。 派生クラスでは、オフセットまたは遷移を指定する必要があります。  
  
##  <a name="m_badded"></a>  CBaseKeyFrame::m_bAdded  
 このキーフレームがストーリー ボードに追加されたかどうかを指定します。  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>  CBaseKeyFrame::m_bIsKeyframeAtOffset  
 このキーフレームをストーリー ボードの別の既存のキーフレームからのオフセットまたはいくつかの遷移の末尾に追加するかどうかを指定します。  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>  CBaseKeyFrame::m_keyframe  
 Windows Animation API キーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START 定義済みの値に設定されます。  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
