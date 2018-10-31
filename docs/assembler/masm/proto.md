---
title: PROTO |Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- PROTO
dev_langs:
- C++
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd00263f3b4a7ffcf23ccd0501989c0d40c637d
ms.sourcegitcommit: f3a5dc788e62bb36e2d9bc3e62e0aa533422408b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49644064"
---
# <a name="proto"></a>PROTO

関数またはプロシージャのプロトタイプ。 関数を呼び出す、プロトタイプ PROTO ディレクティブを使用して、 [INVOKE](invoke.md)ディレクティブ。

## <a name="syntax"></a>構文

> *ラベル* **PROTO** \[*距離*] \[ *langtype*] \[ __、__ \[*パラメーター*]__:__*タグ*].

### <a name="parameters"></a>パラメーター

*label*<br/>
プロトタイプ宣言された関数の名前。

*distance*<br/>
(省略可能)既定値を示す 16 ビットのメモリ モデルで使用される**NEAR**または**FAR**呼び出し。

*langtype*<br/>
(省略可能)プロシージャとパブリック シンボルの呼び出し元と名前付け規則を設定します。 サポートされている規則は次のとおりです。

- 32 ビット**フラット**モデル: **C**、 **STDCALL**

- 16 ビット モデル: **C**、 **BASIC**、 **FORTRAN**、 **PASCAL**、 **SYSCALL**、 **STDCALL**

*parameter*<br/>
関数パラメーターのオプション名。

*タグ*<br/>
関数パラメーターの型。

*パラメーター*と*タグ*パラメーターが渡された引数ごとに複数回を 1 回出現できます。

## <a name="example"></a>例

このサンプルを示しています、 **PROTO**という名前の関数の宣言`addup3`を使用して、 **NEAR**呼び出しを使用してプロシージャの呼び出しの 16 ビットのモデルの既定値を上書きする、 **C**呼び出し規約の stack パラメーターおよび戻り値。 2 つの引数を受け取り、 **WORD**と**VARARG**します。

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](directives-reference.md)<br/>
[.モデルのリファレンス](dot-model.md)<br/>
