---
description: 詳細については、「raw_dispinterfaces import 属性」を参照してください。
title: raw_dispinterfaces インポート属性
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 447f76bdee16d2719c02ad4a73883f8f176f2584
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202016"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces インポート属性

**C++ 固有の仕様**

ディスパッチインターフェイスの下位レベルのラッパー関数を生成するようにコンパイラに指示し `IDispatch::Invoke` ます。また、HRESULT エラーコードを呼び出して返すプロパティを示します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **raw_dispinterfaces**

## <a name="remarks"></a>解説

この属性が指定されていない場合は、上位レベルのラッパーのみが生成されます。この場合、エラー発生時に C++ 例外がスローされます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
