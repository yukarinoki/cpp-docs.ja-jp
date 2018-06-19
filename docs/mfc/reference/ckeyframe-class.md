---
title: CKeyFrame クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
dev_langs:
- C++
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a9e9ff3d6e3e4bcccf8e9ebd46f791f60f1cc37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367186"
---
# <a name="ckeyframe-class"></a>CKeyFrame クラス
アニメーションのキーフレームを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::CKeyFrame](#ckeyframe)|オーバーロードされます。 その他のキーフレームに依存するキーフレームを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::AddToStoryboard](#addtostoryboard)|ストーリー ボードにキーフレームを追加します。 (上書き[CBaseKeyFrame::AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard))。|  
|[CKeyFrame::AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|移行が完了した後ストーリー ボードにキーフレームを追加します。|  
|[CKeyFrame::AddToStoryboardAtOffset](#addtostoryboardatoffset)|ストーリー ボードのオフセット位置にキーフレームを追加します。|  
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|このキーフレームが異なりますキーフレームへのポインターを返します。|  
|[CKeyFrame::GetOffset](#getoffset)|その他のキーフレームからのオフセットを返します。|  
|[CKeyFrame::GetTransition](#gettransition)|このキーフレームが異なります遷移へのポインターを返します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CKeyFrame::m_offset](#m_offset)|このキーフレーム m_pExistingKeyFrame に格納されているキーフレームからのオフセットを指定します。|  
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset とストーリー ボードに追加されます。|  
|[CKeyFrame::m_pTransition](#m_ptransition)|このキーフレームで始まる切り替え効果を指すポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、アニメーションのキーフレームを実装します。 キーフレームは、ストーリー ボード内の特定の時点を表し、遷移の開始と終了時刻を指定するために使用できます。 キーフレーム他のキーフレームに基づいて、そこから秒単位でのオフセットを持ってまたは遷移に基づいてし、この遷移の終了時刻の時点を表します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>  CKeyFrame::AddToStoryboard  
 ストーリー ボードにキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 キーフレームを追加または再帰的に移行するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームが正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードにキーフレームを追加します。 BDeepAdd TRUE は、他のキーフレームや遷移に依存している場合、このメソッドは、再帰的に追加しようとします。  
  
##  <a name="addtostoryboardaftertransition"></a>  CKeyFrame::AddToStoryboardAfterTransition  
 移行が完了した後ストーリー ボードにキーフレームを追加します。  
  
```  
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 遷移の再帰的に追加するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームが正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 この関数は、移行が完了した後ストーリー ボードにキーフレームを追加するためにフレームワークによって呼び出されます。  
  
##  <a name="addtostoryboardatoffset"></a>  CKeyFrame::AddToStoryboardAtOffset  
 ストーリー ボードのオフセット位置にキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 キーフレームを追加するこのキーフレームが再帰的に依存するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーフレームが正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 この関数は、ストーリー ボードのオフセット位置にキーフレームを追加するためにフレームワークによって呼び出されます。  
  
##  <a name="ckeyframe"></a>  CKeyFrame::CKeyFrame  
 遷移に依存するキーフレームを構築します。  
  
```  
CKeyFrame(CBaseTransition* pTransition);

 
CKeyFrame(
    CBaseKeyFrame* pKeyframe,  
    UI_ANIMATION_SECONDS offset = 0.0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTransition`  
 遷移へのポインター。  
  
 `pKeyframe`  
 キーフレームへのポインター。  
  
 `offset`  
 PKeyframe で指定されたキーフレームからの秒数でオフセットします。  
  
### <a name="remarks"></a>コメント  
 指定した遷移の終了時に、構築されたキーフレームはストーリー ボード内の特定の時点を表します。  
  
##  <a name="getexistingkeyframe"></a>  CKeyFrame::GetExistingKeyframe  
 このキーフレームが異なりますキーフレームへのポインターを返します。  
  
```  
CBaseKeyFrame* GetExistingKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレーム、またはこのキーフレームが他のキーフレームに依存しない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 これは、このキーフレームが異なりますキーフレームへアクセサーです。  
  
##  <a name="getoffset"></a>  CKeyFrame::GetOffset  
 その他のキーフレームからのオフセットを返します。  
  
```  
UI_ANIMATION_SECONDS GetOffset();
```  
  
### <a name="return-value"></a>戻り値  
 その他のキーフレームからの秒数でオフセットします。  
  
### <a name="remarks"></a>コメント  
 その他のキーフレームからの秒数でオフセットを決定する、このメソッドを呼び出す必要があります。  
  
##  <a name="gettransition"></a>  CKeyFrame::GetTransition  
 このキーフレームが異なります遷移へのポインターを返します。  
  
```  
CBaseTransition* GetTransition();
```  
  
### <a name="return-value"></a>戻り値  
 遷移、またはこのキーフレームが遷移に依存しない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 これは、このキーフレームが異なります遷移にアクセサーです。  
  
##  <a name="m_offset"></a>  CKeyFrame::m_offset  
 このキーフレーム m_pExistingKeyFrame に格納されているキーフレームからのオフセットを指定します。  
  
```  
UI_ANIMATION_SECONDS m_offset;  
```  
  
##  <a name="m_pexistingkeyframe"></a>  CKeyFrame::m_pExistingKeyFrame  
 既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset とストーリー ボードに追加されます。  
  
```  
CBaseKeyFrame* m_pExistingKeyFrame;  
```  
  
##  <a name="m_ptransition"></a>  CKeyFrame::m_pTransition  
 このキーフレームで始まる切り替え効果を指すポインターを格納します。  
  
```  
CBaseTransition* m_pTransition;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
