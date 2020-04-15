---
title: CKeyFrame クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: f535503338a82c7cc70455ae6a08cdab0f13c624
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372292"
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
|[キーフレーム::Cキーフレーム](#ckeyframe)|オーバーロードされます。 他のキーフレームに依存するキーフレームを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cキーフレーム::ストーリーボードに追加](#addtostoryboard)|ストーリーボードにキーフレームを追加します。 [(CBaseKeyFrame をオーバーライドします。:AddTo ストーリーボード](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[遷移後にストーリーボードを追加します。](#addtostoryboardaftertransition)|トランジション後にストーリーボードにキーフレームを追加します。|
|[Cキーフレーム::アドオンストーリーボードアットオフセット](#addtostoryboardatoffset)|キーフレームをストーリーボードにオフセット位置に追加します。|
|[Cキーフレーム::既存のキーフレームを取得します。](#getexistingkeyframe)|このキーフレームが依存するキーフレームへのポインターを返します。|
|[キーフレーム::ゲットオフセット](#getoffset)|他のキーフレームからのオフセットを返します。|
|[キーフレーム::ゲットトランジション](#gettransition)|このキーフレームが依存するトランジションへのポインターを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[キーフレーム::m_offset](#m_offset)|m_pExistingKeyFrameに格納されているキーフレームからのこのキーフレームのオフセットを指定します。|
|[キーフレーム::m_pExistingKeyFrame](#m_pexistingkeyframe)|既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームにm_offsetを付けてストーリーボードに追加されます。|
|[キーフレーム::m_pTransition](#m_ptransition)|このキーフレームで開始されるトランジションへのポインターを格納します。|

## <a name="remarks"></a>解説

このクラスは、アニメーション キーフレームを実装します。 キーフレームは、ストーリーボード内の時間を表し、トランジションの開始時間と終了時間を指定するために使用できます。 キーフレームは、他のキーフレームに基づいて、そのキーフレームからのオフセット (秒単位) を持つ場合もあれば、遷移に基づいて、このトランジションが終了する瞬間を表している場合もあります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[キーフレーム](../../mfc/reference/cbasekeyframe-class.md)

[キーフレーム](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>Cキーフレーム::ストーリーボードに追加

ストーリーボードにキーフレームを追加します。

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボードへのポインター。

*追加*<br/>
キーフレームを追加するか、再帰的にトランジションするかを指定します。

### <a name="return-value"></a>戻り値

TRUE (キーフレームが正常に追加された場合)。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードにキーフレームを追加します。 他のキーフレームまたはトランジションに依存し、bDeepAdd が TRUE の場合、このメソッドは再帰的に追加しようとします。

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>遷移後にストーリーボードを追加します。

トランジション後にストーリーボードにキーフレームを追加します。

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボードへのポインター。

*追加*<br/>
遷移を再帰的に追加するかどうかを指定します。

### <a name="return-value"></a>戻り値

TRUE (キーフレームが正常に追加された場合)。

### <a name="remarks"></a>解説

この関数は、フレームワークによって呼び出され、遷移後にストーリーボードにキーフレームを追加します。

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>Cキーフレーム::アドオンストーリーボードアットオフセット

キーフレームをストーリーボードにオフセット位置に追加します。

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボードへのポインター。

*追加*<br/>
このキーフレームを再帰的に依存するキーフレームを追加するかどうかを指定します。

### <a name="return-value"></a>戻り値

TRUE (キーフレームが正常に追加された場合)。

### <a name="remarks"></a>解説

この関数は、オフセット時にストーリーボードにキーフレームを追加するために、フレームワークによって呼び出されます。

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a>キーフレーム::Cキーフレーム

トランジションに依存するキーフレームを作成します。

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>パラメーター

*移行*<br/>
遷移へのポインター。

*pキーフレーム*<br/>
キーフレームへのポインター。

*offset*<br/>
pKeyframe で指定されたキーフレームからのオフセット (秒単位)。

### <a name="remarks"></a>解説

構築されたキーフレームは、指定されたトランジションが終了したときにストーリーボード内の瞬間を表します。

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>Cキーフレーム::既存のキーフレームを取得します。

このキーフレームが依存するキーフレームへのポインターを返します。

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター、またはこのキーフレームが他のキーフレームに依存しない場合は NULL。

### <a name="remarks"></a>解説

このキーフレームが依存するキーフレームのアクセサーです。

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a>キーフレーム::ゲットオフセット

他のキーフレームからのオフセットを返します。

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>戻り値

他のキーフレームからのオフセット (秒単位)。

### <a name="remarks"></a>解説

このメソッドは、他のキーフレームからのオフセットを秒単位で決定するために呼び出す必要があります。

## <a name="ckeyframegettransition"></a><a name="gettransition"></a>キーフレーム::ゲットトランジション

このキーフレームが依存するトランジションへのポインターを返します。

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>戻り値

トランジションへの有効なポインター、またはこのキーフレームがトランジションに依存しない場合は NULL。

### <a name="remarks"></a>解説

これは、このキーフレームが依存するトランジションのアクセサーです。

## <a name="ckeyframem_offset"></a><a name="m_offset"></a>キーフレーム::m_offset

m_pExistingKeyFrameに格納されているキーフレームからのこのキーフレームのオフセットを指定します。

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>キーフレーム::m_pExistingKeyFrame

既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームにm_offsetを付けてストーリーボードに追加されます。

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a>キーフレーム::m_pTransition

このキーフレームで開始されるトランジションへのポインターを格納します。

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
