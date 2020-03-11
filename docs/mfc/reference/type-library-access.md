---
title: タイプ ライブラリ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 23d4675bd3638d2effd1b967f0729f9e70dac6de
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867035"
---
# <a name="type-library-access"></a>タイプ ライブラリ アクセス

タイプライブラリは、OLE コントロールのインターフェイスを他の OLE 対応アプリケーションに公開します。 1つ以上のインターフェイスを公開する場合は、各 OLE コントロールにタイプライブラリが必要です。

次のマクロを使用すると、OLE コントロールは独自のタイプライブラリへのアクセスを提供できます。

### <a name="type-library-access"></a>タイプ ライブラリ アクセス

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|OLE コントロールの `GetTypeLib` メンバー関数を宣言します (クラス宣言で使用する必要があります)。|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|OLE コントロールの `GetTypeLib` メンバー関数を実装します (クラスの実装で使用する必要があります)。|

##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

コントロールクラスの `GetTypeLib` メンバー関数を宣言します。

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
タイプライブラリに関連するコントロールクラスの名前。

### <a name="remarks"></a>コメント

このマクロは、コントロールクラスのヘッダーファイルで使用します。

### <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

コントロールの `GetTypeLib` メンバー関数を実装します。

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
タイプライブラリに関連するコントロールクラスの名前。

*tlid*<br/>
タイプライブラリの ID 番号。

*wVerMajor*<br/>
タイプライブラリのメジャーバージョン番号。

*wVerMinor*<br/>
タイプライブラリのマイナーバージョン番号。

### <a name="remarks"></a>コメント

このマクロは、DECLARE_OLETYPELIB マクロを使用するコントロールクラスの実装ファイルに記述されている必要があります。

### <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>参照

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
