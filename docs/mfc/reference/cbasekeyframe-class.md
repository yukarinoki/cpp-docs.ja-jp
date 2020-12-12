---
description: '詳細情報: CBaseKeyFrame フレームクラス'
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
ms.openlocfilehash: 0bebd91183eab9be71e8df4928dc621565718cb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261258"
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
|[CBaseKeyFrame フレーム:: CBaseKeyFrame フレーム](#cbasekeyframe)|キーフレームオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBaseKeyFrame フレーム:: AddToStoryboard](#addtostoryboard)|ストーリーボードにキーフレームを追加します。|
|[CBaseKeyFrame フレーム:: Getアニメーションキーフレーム](#getanimationkeyframe)|基になるキーフレームの値を返します。|
|[CBaseKeyFrame フレーム:: IsAdded](#isadded)|キーフレームがストーリーボードに追加されたかどうかを示します。|
|[CBaseKeyFrame:: Iskeyフレーム Atoffset](#iskeyframeatoffset)|キーフレームをオフセットでストーリーボードに追加するか、または切り替えた後に追加するかを指定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CBaseKeyFrame フレーム:: m_bAdded](#m_badded)|このキーフレームがストーリーボードに追加されたかどうかを指定します。|
|[CBaseKeyFrame フレーム:: m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|このキーフレームを別の既存のキーフレームのオフセット、または一部の遷移の終了時にストーリーボードに追加するかどうかを指定します。|
|[CBaseKeyFrame フレーム:: m_keyframe](#m_keyframe)|Windows アニメーション API のキーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START 定義済みの値に設定されます。|

## <a name="remarks"></a>解説

UI_ANIMATION_KEYFRAME 変数をカプセル化します。 キーフレーム実装の基本クラスとして機能します。 キーフレームは、ストーリーボード内の特定の時点を表し、遷移の開始時刻と終了時刻を指定するために使用できます。 指定されたオフセット (時間単位) で、または指定された遷移の後に追加されたキーフレームに、2種類のキーフレームが追加されています。 一部の遷移の期間はアニメーションの開始前にはわからないため、一部のキーフレームの実際の値は実行時にのみ決定されます。 キーフレームは、キーフレームに依存する遷移に依存している場合があるため、キーフレームチェーンを構築するときに無限の再帰を防ぐことが重要です。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseKeyFrame フレーム:: AddToStoryboard

ストーリーボードにキーフレームを追加します。

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボードへのポインター。

*bDeepAdd*<br/>
このパラメーターが TRUE で、追加されているキーフレームが他のキーフレームまたは遷移に依存している場合、このメソッドはこのキーフレームを追加しようとします。

### <a name="return-value"></a>戻り値

キーフレームがストーリーボードに正常に追加された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードにキーフレームを追加するために呼び出されます。

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a> CBaseKeyFrame フレーム:: CBaseKeyFrame フレーム

キーフレームオブジェクトを構築します。

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a> CBaseKeyFrame フレーム:: Getアニメーションキーフレーム

基になるキーフレームの値を返します。

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>戻り値

現在のキーフレーム。 既定値は UI_ANIMATION_KEYFRAME_STORYBOARD_START です。

### <a name="remarks"></a>解説

これは、基になるキーフレーム値へのアクセサーです。

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a> CBaseKeyFrame フレーム:: IsAdded

キーフレームがストーリーボードに追加されたかどうかを示します。

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>戻り値

ストーリーボードにキーフレームを追加する場合は TRUE。otehrwise FALSE。

### <a name="remarks"></a>解説

では、基本クラス IsAdded は常に TRUE を返しますが、派生クラスではオーバーライドされます。

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a> CBaseKeyFrame:: Iskeyフレーム Atoffset

キーフレームをオフセットでストーリーボードに追加するか、または切り替えた後に追加するかを指定します。

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>戻り値

指定したオフセットで、ストーリーボードにキーフレームを追加する必要がある場合は TRUE。 ある遷移の後に、キーフレームをストーリーボードに追加する必要がある場合は FALSE。

### <a name="remarks"></a>解説

オフセットでストーリーボードにキーフレームを追加する必要があるかどうかを指定します。 オフセットまたは遷移は、派生クラスで指定する必要があります。

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a> CBaseKeyFrame フレーム:: m_bAdded

このキーフレームがストーリーボードに追加されたかどうかを指定します。

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a> CBaseKeyFrame フレーム:: m_bIsKeyframeAtOffset

このキーフレームを別の既存のキーフレームのオフセット、または一部の遷移の終了時にストーリーボードに追加するかどうかを指定します。

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a> CBaseKeyFrame フレーム:: m_keyframe

Windows アニメーション API のキーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START 定義済みの値に設定されます。

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
