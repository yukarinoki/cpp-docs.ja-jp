---
title: タイプ ライブラリ アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 55d6a56f566416bb25f3ee3ae508c86f17f0df99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840454"
---
# <a name="type-library-access"></a>タイプ ライブラリ アクセス

タイプライブラリは、OLE コントロールのインターフェイスを他の OLE 対応アプリケーションに公開します。 1つ以上のインターフェイスを公開する場合は、各 OLE コントロールにタイプライブラリが必要です。

次のマクロを使用すると、OLE コントロールは独自のタイプライブラリへのアクセスを提供できます。

### <a name="type-library-access"></a>タイプ ライブラリ アクセス

|名前|説明|
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|`GetTypeLib`OLE コントロールのメンバー関数を宣言します (クラス宣言で使用する必要があります)。|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|`GetTypeLib`OLE コントロールのメンバー関数を実装します (クラスの実装で使用する必要があります)。|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a> DECLARE_OLETYPELIB

`GetTypeLib`コントロールクラスのメンバー関数を宣言します。

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
タイプライブラリに関連するコントロールクラスの名前。

### <a name="remarks"></a>解説

このマクロは、コントロールクラスのヘッダーファイルで使用します。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a> IMPLEMENT_OLETYPELIB

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

### <a name="remarks"></a>解説

このマクロは、DECLARE_OLETYPELIB マクロを使用するコントロールクラスの実装ファイルに記述されている必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
