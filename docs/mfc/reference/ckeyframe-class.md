---
description: '詳細情報: CKeyFrame フレームクラス'
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
ms.openlocfilehash: ec6aa45484965afbf0c636a1eed26a3d4a63e426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236881"
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
|[CKeyFrame フレーム:: CKeyFrame フレーム](#ckeyframe)|オーバーロードされます。 他のキーフレームに依存するキーフレームを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CKeyFrame フレーム:: AddToStoryboard](#addtostoryboard)|ストーリーボードにキーフレームを追加します。 ( [Cbasekeyframe フレーム:: AddToStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard)をオーバーライドします)。|
|[CKeyFrame フレーム:: AddToStoryboardAfterTransition](#addtostoryboardaftertransition)|遷移後に、ストーリーボードにキーフレームを追加します。|
|[CKeyFrame フレーム:: AddToStoryboardAtOffset](#addtostoryboardatoffset)|オフセットでストーリーボードにキーフレームを追加します。|
|[CKeyFrame フレーム:: GetExistingKeyframe フレーム](#getexistingkeyframe)|このキーフレームが依存するキーフレームへのポインターを返します。|
|[CKeyFrame フレーム:: GetOffset](#getoffset)|他のキーフレームからのオフセットを返します。|
|[CKeyFrame フレーム:: GetTransition](#gettransition)|このキーフレームが依存する遷移へのポインターを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CKeyFrame フレーム:: m_offset](#m_offset)|M_pExistingKeyFrame に格納されているキーフレームから、このキーフレームのオフセットを指定します。|
|[CKeyFrame フレーム:: m_pExistingKeyFrame](#m_pexistingkeyframe)|既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset を持つストーリーボードに追加されます。|
|[CKeyFrame フレーム:: m_pTransition](#m_ptransition)|このキーフレームから開始する transtion へのポインターを格納します。|

## <a name="remarks"></a>解説

このクラスは、アニメーションのキーフレームを実装します。 キーフレームは、ストーリーボード内の特定の時点を表し、遷移の開始時刻と終了時刻を指定するために使用できます。 キーフレームは、他のキーフレームに基づいていて、そこからのオフセット (秒単位) があるか、または遷移に基づいており、この遷移が終了した時点を表している可能性があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a> CKeyFrame フレーム:: AddToStoryboard

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
キーフレームまたは遷移を再帰的に追加するかどうかを指定します。

### <a name="return-value"></a>戻り値

キーフレームが正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードにキーフレームを追加します。 他のキーフレームまたは遷移に依存し、bDeepAdd が TRUE の場合、このメソッドは再帰的に追加しようとします。

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a> CKeyFrame フレーム:: AddToStoryboardAfterTransition

遷移後に、ストーリーボードにキーフレームを追加します。

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボードへのポインター。

*bDeepAdd*<br/>
遷移を再帰的に追加するかどうかを指定します。

### <a name="return-value"></a>戻り値

キーフレームが正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

この関数は、遷移後に、ストーリーボードにキーフレームを追加するためにフレームワークによって呼び出されます。

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a> CKeyFrame フレーム:: AddToStoryboardAtOffset

オフセットでストーリーボードにキーフレームを追加します。

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボードへのポインター。

*bDeepAdd*<br/>
キーフレームを追加するかどうかを指定します。このキーフレームは再帰的に依存します。

### <a name="return-value"></a>戻り値

キーフレームが正常に追加された場合は TRUE。

### <a name="remarks"></a>解説

この関数は、オフセットでストーリーボードにキーフレームを追加するためにフレームワークによって呼び出されます。

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a> CKeyFrame フレーム:: CKeyFrame フレーム

遷移に依存するキーフレームを構築します。

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>パラメーター

*pTransition*<br/>
遷移へのポインター。

*pKeyframe*<br/>
キーフレームへのポインター。

*offset*<br/>
PKeyframe フレームによって指定されたキーフレームからのオフセット (秒単位)。

### <a name="remarks"></a>解説

構築されたキーフレームは、指定された遷移が終了したときにストーリーボード内の特定の時点を表します。

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a> CKeyFrame フレーム:: GetExistingKeyframe フレーム

このキーフレームが依存するキーフレームへのポインターを返します。

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>戻り値

キーフレームへの有効なポインター。このキーフレームが他のキーフレームに依存しない場合は NULL。

### <a name="remarks"></a>解説

これは、このキーフレームが依存するキーフレームのアクセサーです。

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a> CKeyFrame フレーム:: GetOffset

他のキーフレームからのオフセットを返します。

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>戻り値

他のキーフレームからの秒単位のオフセット。

### <a name="remarks"></a>解説

このメソッドは、他のキーフレームからのオフセット (秒単位) を決定するために呼び出す必要があります。

## <a name="ckeyframegettransition"></a><a name="gettransition"></a> CKeyFrame フレーム:: GetTransition

このキーフレームが依存する遷移へのポインターを返します。

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>戻り値

遷移する有効なポインター。このキーフレームが遷移に依存しない場合は NULL。

### <a name="remarks"></a>解説

これは、このキーフレームが依存する遷移のアクセサーです。

## <a name="ckeyframem_offset"></a><a name="m_offset"></a> CKeyFrame フレーム:: m_offset

M_pExistingKeyFrame に格納されているキーフレームから、このキーフレームのオフセットを指定します。

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a> CKeyFrame フレーム:: m_pExistingKeyFrame

既存の keframe へのポインターを格納します。 このキーフレームは、既存のキーフレームに m_offset を持つストーリーボードに追加されます。

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a> CKeyFrame フレーム:: m_pTransition

このキーフレームから開始する transtion へのポインターを格納します。

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
