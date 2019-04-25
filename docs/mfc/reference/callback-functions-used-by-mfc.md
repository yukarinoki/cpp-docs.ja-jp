---
title: MFC で使われているコールバック関数
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.functions
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: e3440530dfe30b6667012c76b2904dbb2786c199
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152151"
---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数

次の 3 つのコールバック関数は、Microsoft Foundation Class ライブラリに表示されます。 これらのコールバック関数に渡される[cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects)、 [cdc::graystring](../../mfc/reference/cdc-class.md#graystring)、および[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)します。 すべてのコールバック関数がコールバックの境界を越えて例外をスローすることはできませんので、Windows に戻る前に MFC の例外をトラップする必要がありますに注意してください。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)します。

|名前||
|----------|-----------------|
|[CDC::EnumObjects 用コールバック関数](#enum_objects)||
|[CDC::GrayString 用コールバック関数](#graystring)||
|[CDC::SetAbortProc 用コールバック関数](#setabortproc)||

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="enum_objects"></a> Cdc::enumobjects 用コールバック関数

*ObjectFunc*名は、アプリケーションによって提供される関数名のプレース ホルダーです。

### <a name="syntax"></a>構文

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>パラメーター

*lpszLogObject*<br/>
指す、 [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen)または[LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush)オブジェクトの論理の属性に関する情報を含むデータ構造です。

*lpData*<br/>
アプリケーションによって提供されるデータへのポインターが渡される、`EnumObjects`関数。

### <a name="return-value"></a>戻り値

コールバック関数が返す、 **int**します。この戻り値の値は、ユーザー定義します。 コールバック関数は 0 を返す場合`EnumObjects`早い段階で列挙を停止します。

### <a name="remarks"></a>Remarks

実際の名前をエクスポートする必要があります。

## <a name="graystring"></a>  Cdc::graystring 用コールバック関数

*OutputFunc*アプリケーションによって提供されるコールバック関数名のプレース ホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>パラメーター

*hDC*<br/>
少なくとものビットマップをメモリ デバイス コンテキストを識別します。 幅と高さで指定された`nWidth`と`nHeight`に`GrayString`します。

*lpData*<br/>
描画される文字列を指します。

*nCount*<br/>
出力する文字数を指定します。

### <a name="return-value"></a>戻り値

コールバック関数の戻り値が成功した場合は TRUE にする必要があります。それ以外の場合は、FALSE です。

### <a name="remarks"></a>Remarks

コールバック関数 (*OutputFunc*) 座標 (0, 0) を基準として、イメージを描画する必要がありますのではなく (*x*、 *y*)。

## <a name="setabortproc"></a>  Cdc::setabortproc 用コールバック関数

名前*AbortFunc*アプリケーションによって提供される関数名のプレース ホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>パラメーター

*hPr*<br/>
デバイス コンテキストを識別します。

*code*<br/>
エラーが発生したかどうかを指定します。 エラーが発生していない場合は 0 になります。 させることでよりプリント マネージャーがディスク領域が現在しより多くのディスク領域が利用可能になる場合は、アプリケーションが待機します。 場合*コード*させることよりは、アプリケーションは、印刷ジョブを中止する必要はありません。 そうでない場合に呼び出すことによって、プリント マネージャーに譲渡する必要があります、`PeekMessage`または`GetMessage`Windows 関数。

### <a name="return-value"></a>戻り値

中止ハンドラー関数の戻り値が 0 以外の場合、印刷ジョブの操作を続行する場合、0 がキャンセルされた場合。

### <a name="remarks"></a>Remarks

」の「解説」の説明に従って、実際の名前をエクスポートする必要があります[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)します。

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)
