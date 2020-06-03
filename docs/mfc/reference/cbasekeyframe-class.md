---
title: CBaseKeyFrame クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 3fcd55f6a157f4b837090a3608fb509b870aae5d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352986"
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
|[キーフレーム::Cベースキーフレーム](#cbasekeyframe)|キーフレーム オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ストーリーボードを追加します。](#addtostoryboard)|ストーリーボードにキーフレームを追加します。|
|[フレーム::アニメーションキーフレームを取得します。](#getanimationkeyframe)|基になるキーフレーム値を返します。|
|[キーフレーム::追加されました](#isadded)|キーフレームがストーリーボードに追加されたかどうかを示します。|
|[キーフレーム::イズキーフレームアットオフセット](#iskeyframeatoffset)|キーフレームをオフセット時にストーリーボードに追加するか、またはトランジション後に追加するかを指定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[キーフレーム::m_bAdded](#m_badded)|このキーフレームがストーリーボードに追加されているかどうかを指定します。|
|[キーフレーム::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|このキーフレームを、別の既存のキーフレームからのオフセットでストーリーボードに追加するか、何らかのトランジションの最後に追加するかを指定します。|
|[m_keyframe](#m_keyframe)|Windows アニメーション API のキーフレームを表します。 キーフレームが初期化されていない場合、定義済みの値UI_ANIMATION_KEYFRAME_STORYBOARD_STARTに設定されます。|

## <a name="remarks"></a>解説

変数UI_ANIMATION_KEYFRAMEカプセル化します。 キーフレームの実装の基本クラスとして機能します。 キーフレームは、ストーリーボード内の時間を表し、トランジションの開始時間と終了時間を指定するために使用できます。 キーフレームには、指定したオフセット (時間) でストーリーボードに追加されるキーフレームと、指定したトランジション後に追加されるキーフレームの 2 種類があります。 アニメーションが開始される前に一部のトランジションの継続時間を認識できないため、一部のキーフレームの実際の値は実行時にのみ決定されます。 キーフレームはトランジションに依存する場合があるため、キーフレームの順番はキーフレームに依存するため、キーフレームチェーンを構築する際に無限の再帰を防ぐことが重要です。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>ストーリーボードを追加します。

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
このパラメータが TRUE で、追加されるキーフレームが他のキーフレームまたはトランジションに依存する場合、このメソッドは、このキーフレームを追加するか、最初にストーリーボードに遷移しようとします。

### <a name="return-value"></a>戻り値

ストーリーボードにキーフレームが正常に追加された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードにキーフレームを追加するために呼び出されます。

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a>キーフレーム::Cベースキーフレーム

キーフレーム オブジェクトを作成します。

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a>フレーム::アニメーションキーフレームを取得します。

基になるキーフレーム値を返します。

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>戻り値

現在のキーフレーム。 既定値は UI_ANIMATION_KEYFRAME_STORYBOARD_START です。

### <a name="remarks"></a>解説

これは、基になるキーフレーム値のアクセサーです。

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a>キーフレーム::追加されました

キーフレームがストーリーボードに追加されたかどうかを示します。

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>戻り値

ストーリーボードにキーフレームが追加された場合は TRUE。オースワイズ偽。

### <a name="remarks"></a>解説

基本クラスでは、IsAdded は常に TRUE を返しますが、派生クラスでオーバーライドされます。

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a>キーフレーム::イズキーフレームアットオフセット

キーフレームをオフセット時にストーリーボードに追加するか、またはトランジション後に追加するかを指定します。

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、キーフレームを指定したオフセットでストーリーボードに追加する必要があります。 何らかのトランジションの後にキーフレームをストーリーボードに追加する必要がある場合は FALSE。

### <a name="remarks"></a>解説

キーフレームをオフセット時にストーリーボードに追加するかどうかを指定します。 オフセットまたは遷移は、派生クラスで指定する必要があります。

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a>キーフレーム::m_bAdded

このキーフレームがストーリーボードに追加されているかどうかを指定します。

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a>キーフレーム::m_bIsKeyframeAtOffset

このキーフレームを、別の既存のキーフレームからのオフセットでストーリーボードに追加するか、何らかのトランジションの最後に追加するかを指定します。

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a>m_keyframe

Windows アニメーション API のキーフレームを表します。 キーフレームが初期化されていない場合、定義済みの値UI_ANIMATION_KEYFRAME_STORYBOARD_STARTに設定されます。

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
