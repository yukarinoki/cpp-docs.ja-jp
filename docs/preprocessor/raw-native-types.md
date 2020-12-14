---
description: 詳細については、「raw_native_types import 属性」を参照してください。
title: raw_native_types インポート属性
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 64eaadcbb3d9f07d47dd4a33bc16a222cae50f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240534"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types インポート属性

**C++ 固有の仕様**

高レベルのラッパー関数での COM サポートクラスの使用を無効にし、代わりに下位レベルのデータ型を強制的に使用します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **raw_native_types**

## <a name="remarks"></a>解説

既定では、高レベルのエラー処理メソッドは、 [](../cpp/bstr-t-class.md)および[](../cpp/variant-t-class.md) `BSTR` `VARIANT` データ型と生の com インターフェイスポインターの代わりに、com サポートクラス _bstr_t および _variant_t を使用します。 これらのクラスは、これらのデータ型のメモリ ストレージの割り当てと解放の詳細情報をカプセル化し、型キャストと変換演算を大幅に簡略化します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
