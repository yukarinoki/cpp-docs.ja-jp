---
description: '詳細については、次を参照してください: _fmode'
title: _fmode
ms.date: 11/04/2016
f1_keywords:
- fmode
- _fmode
helpviewer_keywords:
- file translation [C++], default mode
- fmode function
- _fmode function
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
ms.openlocfilehash: c4e7932369a2ad63b5498078e46cd5610b679ee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303891"
---
# <a name="_fmode"></a>_fmode

`_fmode` 変数では、テキストまたはバイナリの変換のための既定のファイル変換モードを設定します。 このグローバル変数は非推奨とされました。セキュリティを強化したバージョンである [_get_fmode](../c-runtime-library/reference/get-fmode.md) および [_set_fmode](../c-runtime-library/reference/set-fmode.md) を、グローバル変数の代わりに使用する必要があります。 これは、Stdlib.h で次のように宣言されています。

## <a name="syntax"></a>構文

```
extern int _fmode;
```

## <a name="remarks"></a>解説

`_fmode` の既定の設定は、テキスト モード用の `_O_TEXT` です。 `_O_BINARY` はバイナリ モード用の設定です。

`_fmode` の値は、次の 3 つの方法で変更できます。

- Binmode .obj にリンクします。これにより、の初期設定が `_fmode` に変更 `_O_BINARY` され、、、およびを除くすべてのファイル `stdin` `stdout` `stderr` がバイナリモードで開かれます。

- `_get_fmode` または `_set_fmode` を呼び出して、`_fmode` グローバル変数を取得または設定します。

- `_fmode` をプログラム内に設定してその値を直接変更します。

## <a name="see-also"></a>関連項目

[グローバル変数](../c-runtime-library/global-variables.md)<br/>
[_get_fmode](../c-runtime-library/reference/get-fmode.md)<br/>
[_set_fmode](../c-runtime-library/reference/set-fmode.md)
