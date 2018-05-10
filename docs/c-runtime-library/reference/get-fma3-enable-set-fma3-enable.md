---
title: _get_FMA3_enable、_set_FMA3_enable |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_FMA3_enable
- _set_FMA3_enable
apilocation:
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
- math/_get_FMA3_enable
- math/_set_FMA3_enable
dev_langs:
- C++
helpviewer_keywords:
- _get_FMA3_enable
- _set_FMA3_enable
ms.assetid: 4c1dc4bc-e86b-451b-9211-5a2ba6c98ee4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e9f3058f4b8ebc59ba58460ba122cab063a5059
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="getfma3enable-setfma3enable"></a>_get_FMA3_enable、_set_FMA3_enable

X64 用に、超越 math 浮動小数点ライブラリ関数がコンパイルされたコードで FMA3 手順を使用するかどうかを指定するフラグを設定を取得またはプラットフォームです。

## <a name="syntax"></a>構文

```C
int _set_FMA3_enable(int flag);
int _get_FMA3_enable();
```

### <a name="parameters"></a>パラメーター

*flag*<br/>
1 に設定すると、x64 超越数値演算ライブラリの浮動小数点関数の FMA3 実装を有効にするプラットフォームでは、または FMA3 命令は使用されませんの実装を使用する場合は 0 にします。

## <a name="return-value"></a>戻り値

超越数値演算ライブラリの浮動小数点関数の FMA3 実装が有効な場合は 0 以外の値。 それ以外の場合、0 を返します。

## <a name="remarks"></a>コメント

使用して、 **_set_FMA3_enable**を有効にするにまたは CRT ライブラリで超越 math 浮動小数点関数内の FMA3 命令の使用を無効にします。 戻り値には、使用されて、変更後の実装が反映されます。 CPU が FMA3 命令をサポートしていない場合は、この関数をライブラリで有効にすることはできませんし、戻り値は 0 です。 使用して **_get_FMA3_enable**ライブラリの現在の状態を取得します。 既定では、x64 プラットフォームでは、CRT スタートアップ コードは、CPU について、FMA3 手順についてをサポートしているとを有効にまたはライブラリに FMA3 実装が無効になりますでかどうかを検出します。

FMA3 実装を有効または無効になっている、またはか FMA3 をサポートしているコンピューター間で FMA3 実装では、異なるアルゴリズムを使用するためには、計算の結果にわずかな相違点で観測可能なオブジェクト可能性があります。 詳細については、次を参照してください。[浮動小数点の移行に関する問題](../../porting/floating-point-migration-issues.md)です。

## <a name="requirements"></a>要件

**_Set_FMA3_enable**と **_get_FMA3_enable**関数だけでは使用 X64 バージョンの CRT です。

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_FMA3_enable**、 **_get_FMA3_enable**| C: \<math.h><br />C++: \<cmath > または\<math.h >|

**_Set_FMA3_enable**と **_get_FMA3_enable**関数は、Microsoft 固有の仕様です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[浮動小数点の移行に関する問題](../../porting/floating-point-migration-issues.md)<br/>
