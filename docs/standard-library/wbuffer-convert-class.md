---
title: wbuffer_convert クラス
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: ba8c98075741ae6cb8db0ecdfcb1e18cf4f4f89c
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561116"
---
# <a name="wbuffer_convert-class"></a>wbuffer_convert クラス

バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。

## <a name="syntax"></a>構文

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>パラメーター

*Codecvt*\
変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。

*Elem*\
ワイド文字要素型。

*名札*\
*Elem* と関連付けられている特徴。

## <a name="remarks"></a>解説

このクラステンプレートは、型の要素の転送を制御するストリームバッファーを記述します。これは、文字の特徴がクラスによって記述されている型の要素の転送を、 `_Elem` `Traits` 型のバイトストリームバッファーとの間で制御し `std::streambuf` ます。

`Elem` 値のシーケンスとマルチバイト シーケンスとの間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。

このクラステンプレートのオブジェクトは、次のものを格納します。

- 基になるバイト ストリーム バッファーへのポインター

- 割り当てられた変換オブジェクトへのポインター ([wbuffer_convert](../standard-library/wbuffer-convert-class.md) のときに解放される)
