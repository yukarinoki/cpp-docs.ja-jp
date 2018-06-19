---
title: MFC で使用されるコールバック関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce96d90506176812ffb70b580c9d95a38c65fa19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350886"
---
# <a name="callback-functions-used-by-mfc"></a>MFC で使われているコールバック関数
次の 3 つのコールバック関数は、Microsoft Foundation Class ライブラリに表示されます。 これらのコールバック関数に渡される[cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects)、 [cdc::graystring](../../mfc/reference/cdc-class.md#graystring)、および[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)です。 すべてのコールバック関数がコールバックの境界を越えて例外をスローすることはできませんので、Windows に返す前に MFC 例外をトラップする必要がありますに注意してください。 例外の詳細については、記事を参照してください。[例外](../../mfc/exception-handling-in-mfc.md)です。  

|名前||  
|----------|-----------------|  
|[CDC::EnumObjects 用コールバック関数](#enum_objects)||  
|[CDC::GrayString 用コールバック関数](#graystring)||
|[CDC::SetAbortProc 用コールバック関数](#setabortproc)|| 

## <a name="requirements"></a>要件  
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
 *lpszLogObject*  
 指す、 [LOGPEN](../../mfc/reference/logpen-structure.md)または[LOGBRUSH](../../mfc/reference/logbrush-structure.md)オブジェクトの論理属性に関する情報を格納するデータ構造です。  
  
 `lpData`  
 アプリケーションによって提供されるデータへのポインターが渡される、`EnumObjects`関数。  
  
### <a name="return-value"></a>戻り値  
 コールバック関数が返す、`int`です。 この戻り値の値は、ユーザー定義です。 コールバック関数は 0 を返す場合`EnumObjects`早い段階で列挙を停止します。  
  
### <a name="remarks"></a>コメント  
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
 `hDC`  
 少なくとものビットマップをメモリ デバイス コンテキストを識別の幅と高さで指定された`nWidth`と`nHeight`に`GrayString`です。  
  
 `lpData`  
 描画される文字列を指します。  
  
 `nCount`  
 出力する文字の数を指定します。  
  
### <a name="return-value"></a>戻り値  
 コールバック関数の戻り値である必要があります**TRUE**成功した場合はそれ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 コールバック関数 (*OutputFunc*) 座標 (0, 0) を基準としたイメージを描画する必要がなく (*x*、 *y*)。  

## <a name="setabortproc"></a>  Cdc::setabortproc 用コールバック関数
名前*AbortFunc*アプリケーションによって提供される関数名のプレース ホルダーです。  
  
### <a name="syntax"></a>構文  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPr*  
 デバイス コンテキストを識別します。  
  
 `code`  
 エラーが発生したかどうかを指定します。 エラーが発生していない場合は 0 になります。 **させることでより**プリント マネージャーがディスク領域が不足が現在、多くのディスク領域は、アプリケーションが待機する場合に使用可能になる場合。 場合`code`は**させることでより**アプリケーションは、印刷ジョブを中止する必要はありません。 そうでない場合に呼び出すことにより、プリント マネージャーを生成する必要があります、 **PeekMessage**または**GetMessage** Windows の機能です。  
  
### <a name="return-value"></a>戻り値  
 中止ハンドラー関数の戻り値は、印刷ジョブの操作を続行する場合、0 以外の値、0 が取り消された場合。  
  
### <a name="remarks"></a>コメント  
 」の「解説」セクションの説明に従って実際名前をエクスポートする必要があります[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)です。  
 
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](structures-styles-callbacks-and-message-maps.md) [cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects) [cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc) [cdc::graystring](../../mfc/reference/cdc-class.md#graystring)

