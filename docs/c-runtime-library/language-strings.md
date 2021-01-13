---
title: Language Strings
description: '詳細情報: 言語識別文字列'
ms.date: 1/12/2021
helpviewer_keywords:
- language strings
ms.openlocfilehash: ec82bb8b9efb9c366c287c79b71b60a3c6bc6ab2
ms.sourcegitcommit: b51f79b5394e12cd90cb65c85cc01716f90bfc90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "98167022"
---
# <a name="language-strings"></a>Language Strings

および関数では、 [`setlocale`](../c-runtime-library/reference/setlocale-wsetlocale.md) [`_create_locale`](../c-runtime-library/reference/create-locale-wcreate-locale.md) Unicode コードページを使用しないオペレーティングシステムでサポートされている言語の Windows NLS API を使用できます。 オペレーティングシステムのバージョン別にサポートされる言語の一覧については、「 [付録 a:](/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c) MS Lcid の製品の動作」を参照してください \[ 。 言語識別文字列には、サポートされる言語の一覧の **[Language]** 列と **[Language tag]** 列の任意の値を指定できます。 使用可能なロケール名と関連する値を列挙するコードの例については、「 [NLS: 名前ベースの api のサンプル](/windows/win32/intl/nls--name-based-apis-sample)」を参照してください。

## <a name="supported-language-strings"></a>サポートされている言語文字列

Microsoft の C ランタイム ライブラリの実装では、次の言語識別文字列もサポートされます。

|言語識別文字列|同等のロケール名|
|---------------------|----------------------------|
|`american`|`en-US`|
|`american english`|`en-US`|
|`american-english`|`en-US`|
|`australian`|`en-AU`|
|`belgian`|`nl-BE`|
|`canadian`|`en-CA`|
|`chh`|`zh-HK`|
|`chi`|`zh-SG`|
|`chinese`|`zh`|
|`chinese-hongkong`|`zh-HK`|
|`chinese-simplified`|`zh-CN`|
|`chinese-singapore`|`zh-SG`|
|`chinese-traditional`|`zh-TW`|
|`dutch-belgian`|`nl-BE`|
|`english-american`|`en-US`|
|`english-aus`|`en-AU`|
|`english-belize`|`en-BZ`|
|`english-can`|`en-CA`|
|`english-caribbean`|`en-029`|
|`english-ire`|`en-IE`|
|`english-jamaica`|`en-JM`|
|`english-nz`|`en-NZ`|
|`english-south africa`|`en-ZA`|
|`english-trinidad y tobago`|`en-TT`|
|`english-uk`|`en-GB`|
|`english-us`|`en-US`|
|`english-usa`|`en-US`|
|`french-belgian`|`fr-BE`|
|`french-canadian`|`fr-CA`|
|`french-luxembourg`|`fr-LU`|
|`french-swiss`|`fr-CH`|
|`german-austrian`|`de-AT`|
|`german-lichtenstein`|`de-LI`|
|`german-luxembourg`|`de-LU`|
|`german-swiss`|`de-CH`|
|`irish-english`|`en-IE`|
|`italian-swiss`|`it-CH`|
|`norwegian`|`no`|
|`norwegian-bokmal`|`nb-NO`|
|`norwegian-nynorsk`|`nn-NO`|
|`portuguese-brazilian`|`pt-BR`|
|`spanish-argentina`|`es-AR`|
|`spanish-bolivia`|`es-BO`|
|`spanish-chile`|`es-CL`|
|`spanish-colombia`|`es-CO`|
|`spanish-costa rica`|`es-CR`|
|`spanish-dominican republic`|`es-DO`|
|`spanish-ecuador`|`es-EC`|
|`spanish-el salvador`|`es-SV`|
|`spanish-guatemala`|`es-GT`|
|`spanish-honduras`|`es-HN`|
|`spanish-mexican`|`es-MX`|
|`spanish-modern`|`es-ES`|
|`spanish-nicaragua`|`es-NI`|
|`spanish-panama`|`es-PA`|
|`spanish-paraguay`|`es-PY`|
|`spanish-peru`|`es-PE`|
|`spanish-puerto rico`|`es-PR`|
|`spanish-uruguay`|`es-UY`|
|`spanish-venezuela`|`es-VE`|
|`swedish-finland`|`sv-FI`|
|`swiss`|`de-CH`|
|`uk`|`en-GB`|
|`us`|`en-US`|
|`usa`|`en-US`|

## <a name="see-also"></a>関連項目

- [ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
- [国/地域識別文字列](../c-runtime-library/country-region-strings.md)\
- [`setlocale`, `_wsetlocale`](../c-runtime-library/reference/setlocale-wsetlocale.md)\
- [`_create_locale`, `_wcreate_locale`](../c-runtime-library/reference/create-locale-wcreate-locale.md)
