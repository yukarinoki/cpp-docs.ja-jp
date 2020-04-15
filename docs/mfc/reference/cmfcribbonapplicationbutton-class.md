---
title: CMFCRibbonApplicationButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
helpviewer_keywords:
- CMFCRibbonApplicationButton [MFC], CMFCRibbonApplicationButton
- CMFCRibbonApplicationButton [MFC], SetImage
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
ms.openlocfilehash: 0debd40825990b647cd5b1df9a144e3abd450de3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361606"
---
# <a name="cmfcribbonapplicationbutton-class"></a>CMFCRibbonApplicationButton クラス

アプリケーション ウィンドウの左上隅に表示される特殊なボタンを実装します。 このボタンがクリックされると、通常は、一般的な **[ファイル]** メニューのコマンド ( **[開く]**、 **[上書き保存]**、 **[終了]** など) を含むメニューが開かれます。

## <a name="syntax"></a>構文

```
class CMFCRibbonApplicationButton : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[アプリケーション ボタン::CMFCリボン アプリケーション ボタン](#cmfcribbonapplicationbutton)|`CMFCRibbonApplicationButton` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCRibbonApplicationButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|`CMFCRibbonApplicationButton::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[アプリケーションボタン::セットイメージ](#setimage)|リボン アプリケーション ボタンにイメージを割り当てます。|

## <a name="example"></a>例

`CMFCRibbonApplicationButton` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、アプリケーション ボタンにイメージを割り当てる方法と、そのツールヒントを設定する方法を示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonBar.h

## <a name="cmfcribbonapplicationbuttoncmfcribbonapplicationbutton"></a><a name="cmfcribbonapplicationbutton"></a>アプリケーション ボタン::CMFCリボン アプリケーション ボタン

[オブジェクトを](../../mfc/reference/cmfcribbonapplicationbutton-class.md)構築して初期化します。

```
CMFCRibbonApplicationButton();
CMFCRibbonApplicationButton(UINT uiBmpResID);
CMFCRibbonApplicationButton(HBITMAP hBmp);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
アプリケーション ボタンに表示するイメージのリソース ID。

*hBmp*<br/>
アプリケーション ボタンに表示するビットマップへのハンドル。

### <a name="remarks"></a>解説

リボン アプリケーション ボタンは、アプリケーション ウィンドウの左上隅にある特別なボタンです。 ユーザーがこのボタンをクリックすると、通常は **[開く**]、[**保存**]、[**終了**] などの一般的な**ファイル**コマンドを含むメニューが開きます。

## <a name="cmfcribbonapplicationbuttonsetimage"></a><a name="setimage"></a>アプリケーションボタン::セットイメージ

アプリケーション ボタンにイメージを割り当てます。

```
void SetImage(UINT uiBmpResID);
void SetImage(HBITMAP hBmp);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]アプリケーション ボタンに表示するイメージのリソース ID。

*hBmp*<br/>
[in]アプリケーション ボタンに表示するビットマップへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、ボタンを作成した後で、リボン アプリケーション ボタンに新しいイメージを割り当てる場合に使用します。 アプリケーション ボタンは、アプリケーション ウィンドウの左上隅にあります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
