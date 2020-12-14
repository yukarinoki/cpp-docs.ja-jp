---
description: '詳細情報: CMenuTearOffManager クラス'
title: CMenuTearOffManager クラス
ms.date: 10/18/2018
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
ms.openlocfilehash: b80f2e935f8d1dd47bf19a11522e4556b35490b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336639"
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager クラス

ティアオフ メニューを管理します。 ティアオフ メニューはメニュー バー上のメニューの一種です。 ユーザーは、ティアオフ メニューをメニュー バーから外して、フローティング メニューにすることができます。

   詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMenuTearOffManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|`CMenuTearOffManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMenuTearOffManager:: Build](#build)||
|[CMenuTearOffManager:: GetRegPath](#getregpath)||
|[CMenuTearOffManager:: Initialize](#initialize)|オブジェクトを初期化 `CMenuTearOffManager` します。|
|[CMenuTearOffManager:: IsDynamicID](#isdynamicid)||
|[CMenuTearOffManager::P arse](#parse)||
|[CMenuTearOffManager:: Reset](#reset)||
|[CMenuTearOffManager:: SetInUse](#setinuse)||
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||

## <a name="remarks"></a>解説

アプリケーションでティアオフメニューを使用するには、オブジェクトが必要 `CMenuTearOffManager` です。 ほとんどの場合、オブジェクトを直接作成したり初期化したりすることはありません `CMenuTearOffManager` 。 [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)関数を呼び出すと、この処理が行われます。

## <a name="example"></a>例

次の例は、メソッドを呼び出してオブジェクトを構築および初期化する方法を示して `CMenuTearOffManager` `CWinAppEX::EnableTearOffMenus` います。 このコード スニペットは、 [Word パッド サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMenuTearOffManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxmenutearoffmanager

## <a name="cmenutearoffmanagerbuild"></a><a name="build"></a> CMenuTearOffManager:: Build

```cpp
void Build(
    UINT uiTearOffBarID,
    CString& strText);
```

### <a name="parameters"></a>パラメーター

から *Uitの Offbarid*<br/>

から *strText*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a> CMenuTearOffManager::CMenuTearOffManager

[CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクトを構築します。

```
CMenuTearOffManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、手動でを作成することはできません `CMenuTearOffManager` 。 `CMenuTearOffManager` [CWinAppEx:: EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)を呼び出すと、アプリケーションのフレームワークによってオブジェクトが作成されます。

## <a name="cmenutearoffmanagergetregpath"></a><a name="getregpath"></a> CMenuTearOffManager:: GetRegPath

```
LPCTSTR GetRegPath() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerinitialize"></a><a name="initialize"></a> CMenuTearOffManager:: Initialize

[CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクトを初期化します。

```
BOOL Initialize(
    LPCTSTR lpszRegEntry,
    UINT uiTearOffMenuFirst,
    UINT uiTearOffMenuLast);
```

### <a name="parameters"></a>パラメーター

*lpszRegEntry*<br/>
からレジストリエントリのパスを含む文字列。 アプリケーションでは、このレジストリエントリにティアオフバーの設定を格納します。

*最初のメニュー*<br/>
からティアオフメニューの最初のメニュー ID。

*Uit氏 Offmenulast*<br/>
からティアオフメニューの最後のメニュー ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*最初* から *Uit氏 Offmenulast* のメニュー id の範囲は、連続した間隔である必要があります。 この間隔は、アプリケーションで同時に表示できるティアオフメニューの数を定義します。

## <a name="cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a> CMenuTearOffManager:: IsDynamicID

```
BOOL IsDynamicID(UINT uiID) const;
```

### <a name="parameters"></a>パラメーター

から *uiID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerparse"></a><a name="parse"></a> CMenuTearOffManager::P arse

```
UINT Parse(CString& str);
```

### <a name="parameters"></a>パラメーター

から *str*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagerreset"></a><a name="reset"></a> CMenuTearOffManager:: Reset

```cpp
void Reset(HMENU hmenu);
```

### <a name="parameters"></a>パラメーター

から *hmenu*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagersetinuse"></a><a name="setinuse"></a> CMenuTearOffManager:: SetInUse

```cpp
void SetInUse(
    UINT uiCmdId,
    BOOL bUse = TRUE);
```

### <a name="parameters"></a>パラメーター

から *uiCmdId*<br/>

から *Buse*<br/>

### <a name="remarks"></a>解説

## <a name="cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a> CMenuTearOffManager::SetupTearOffMenus

```cpp
void SetupTearOffMenus(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

から *hMenu*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
