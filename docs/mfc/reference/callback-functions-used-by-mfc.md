---
title: MFC で使われているコールバック関数
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 8d84f939795e768c6b1356dcd8dc291421aedfdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371135"
---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数

3 つのコールバック関数が、Microsoft Foundation クラス ライブラリに表示されます。 これらのコールバック関数は[、CDC:::列挙オブジェクト](../../mfc/reference/cdc-class.md#enumobjects)[、CDC::グレーストリング](../../mfc/reference/cdc-class.md#graystring)、および[CDC::SetAbortProc に渡されます](../../mfc/reference/cdc-class.md#setabortproc)。 例外はコールバック境界を越えてスローできないため、すべてのコールバック関数は、Windows に戻る前に MFC の例外をトラップする必要があります。 例外の詳細については、記事「[例外](../../mfc/exception-handling-in-mfc.md)」を参照してください。

|名前||
|----------|-----------------|
|[CDC::EnumObjects 用コールバック関数](#enum_objects)||
|[CDC::GrayString 用コールバック関数](#graystring)||
|[CDC::SetAbortProc 用コールバック関数](#setabortproc)||

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="callback-function-for-cdcenumobjects"></a><a name="enum_objects"></a>CDC のコールバック関数::列挙オブジェクト

*ObjectFunc*名は、アプリケーションが指定した関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
オブジェクトの論理属性に関する情報を含む[LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen)または[LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush)データ構造体へのポイント。

*lpData*<br/>
`EnumObjects`関数に渡されるアプリケーション提供のデータへのポイント。

### <a name="return-value"></a>戻り値

コールバック関数は**int**を返します。この戻り値の値はユーザー定義です。 コールバック関数が 0 を`EnumObjects`返す場合は、列挙を早めに停止します。

### <a name="remarks"></a>解説

実際の名前をエクスポートする必要があります。

## <a name="callback-function-for-cdcgraystring"></a><a name="graystring"></a>CDC のコールバック関数::グレーストリング

*OutputFunc*は、アプリケーションが指定したコールバック関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>パラメーター

*Hdc*<br/>
によって`nWidth`指定された幅と高さ以上のビットマップを使用`nHeight`してメモリ デバイス コンテキストを識別`GrayString`します。

*lpData*<br/>
描画される文字列を指します。

*nカウント*<br/>
出力する文字数を指定します。

### <a name="return-value"></a>戻り値

成功を示すには、コールバック関数の戻り値を TRUE にする必要があります。それ以外の場合は FALSE です。

### <a name="remarks"></a>解説

コールバック関数 (*OutputFunc*) は *、(x,* *y)* ではなく、座標 (0,0) を基準にしてイメージを描画する必要があります。

## <a name="callback-function-for-cdcsetabortproc"></a><a name="setabortproc"></a>コールバック関数の使用

*AbortFunc*という名前は、アプリケーションが指定した関数名のプレースホルダーです。

### <a name="syntax"></a>構文

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>パラメーター

*hPr*<br/>
デバイス コンテキストを識別します。

*コード*<br/>
エラーが発生したかどうかを指定します。 エラーが発生しなかった場合は 0 です。 プリント マネージャが現在ディスク領域を使い切っていて、アプリケーションが待機した場合に使用可能なディスク領域が増える場合は、SP_OUTOFDISKです。 *コード*がSP_OUTOFDISK場合、アプリケーションは印刷ジョブを中止する必要はありません。 ない場合は、`PeekMessage`または`GetMessage`Windows 関数を呼び出して印刷マネージャーに譲る必要があります。

### <a name="return-value"></a>戻り値

印刷ジョブを続行する場合は、中止ハンドラー関数の戻り値は 0 以外、キャンセルされた場合は 0 です。

### <a name="remarks"></a>解説

実際の名前は[、CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)の解説 セクションで説明されているようにエクスポートする必要があります。

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::列挙オブジェクト](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::セットアボート・プロセス](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::グレイストリング](../../mfc/reference/cdc-class.md#graystring)
