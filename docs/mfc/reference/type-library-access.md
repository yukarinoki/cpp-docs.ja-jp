---
title: タイプ ライブラリ アクセス
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 4dc5a445f4a7736182350c16720686ca7e0bc27c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468381"
---
# <a name="type-library-access"></a>タイプ ライブラリ アクセス

タイプ ライブラリでは、その他の OLE に対応するアプリケーションに OLE コントロールのインターフェイスを公開します。 各 OLE コントロールは、1 つまたは複数のインターフェイスを公開する場合、タイプ ライブラリにすることが必要です。

次のマクロは、独自のタイプ ライブラリへのアクセスを提供する OLE コントロールを許可します。

### <a name="type-library-access"></a>タイプ ライブラリ アクセス

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|宣言を`GetTypeLib`(クラス宣言で使用する必要があります)、OLE コントロールのメンバー関数。|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|実装を`GetTypeLib`(クラスの実装で使用する必要があります)、OLE コントロールのメンバー関数。|

##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB

宣言、`GetTypeLib`コントロール クラスのメンバー関数。

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>パラメーター

*$class_name$*<br/>
タイプ ライブラリに関連するコントロール クラスの名前。

### <a name="remarks"></a>Remarks

コントロール クラスのヘッダー ファイルでこのマクロを使用します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB

コントロールの実装`GetTypeLib`メンバー関数。

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>パラメーター

*$class_name$*<br/>
タイプ ライブラリに関連するコントロール クラスの名前。

*tlid*<br/>
タイプ ライブラリの ID 番号。

*wVerMajor*<br/>
タイプ ライブラリのメジャー バージョン番号。

*wVerMinor*<br/>
タイプ ライブラリのマイナー バージョン番号。

### <a name="remarks"></a>Remarks

このマクロは、DECLARE_OLETYPELIB マクロを使用するコントロール クラスの実装ファイルに表示する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
