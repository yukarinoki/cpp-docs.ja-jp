---
title: ストリームの制御
description: Microsoft C ランタイムライブラリでのストリームの操作の概要について説明します。
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Controlling Streams
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
ms.openlocfilehash: 0caa9eca7c960acbb581358c1a92afcc6a8af066
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589719"
---
# <a name="controlling-streams"></a>ストリームの制御

[fopen](../c-runtime-library/reference/fopen-wfopen.md) は `FILE` 型のオブジェクトのアドレスを返します。 いくつかのライブラリ関数の引数 `stream` としてこのアドレスを使用し、開かれたファイルに対してさまざまな操作を実行します。 バイト ストリームについては、[fgetc](../c-runtime-library/reference/fgetc-fgetwc.md) を呼び出して各文字を読み取るかのようにすべての入力が処理され、[fputc](../c-runtime-library/reference/fputc-fputwc.md) を呼び出して各文字を書き込むかのようにすべての出力が処理されます。 ワイド ストリームについては、[fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md) を呼び出して各文字を読み取るかのようにすべての入力が処理され、[fputwc](../c-runtime-library/reference/fputc-fputwc.md) を呼び出して各文字を書き込むかのようにすべての出力が処理されます。

[fclose](../c-runtime-library/reference/fclose-fcloseall.md) を呼び出すとファイルを閉じることができ、そのあと `FILE` オブジェクトのアドレスは無効になります。

`FILE` オブジェクトは次のようなストリームの状態を格納します。

- 関数が読み取りまたは書き込みのエラーを検出すると 0 以外に設定されるエラー インジケーター。

- 関数が読み取り中にファイルの終端を検出すると 0 以外に設定される EOF インジケーター。

- ストリーム内で次に読み取るまたは書き込むバイトを指定するファイル位置インジケーター (ファイルが位置決め要求をサポートしている場合)。

- ストリームで読み取りまたは書き込み (あるいはその両方) を承認するかどうか、ストリームが非バインド、バイト指向、ワイド指向のいずれであるかを指定する[ストリームの状態](../c-runtime-library/stream-states.md)。

- 一部がアセンブルされた、または生成済みである汎用マルチバイト文字の状態、およびファイル内のバイト シーケンスのシフト状態を記憶する変換の状態。

- ライブラリ関数がストリームの読み取りまたは書き込みのパフォーマンス改善に使用できる配列オブジェクトのアドレスおよびサイズを指定するファイル バッファー。

`FILE` オブジェクト、またはそのオブジェクトと使用するために指定したファイル バッファーに格納されている値は変更しないでください。 `FILE` オブジェクトをコピーすること、およびそのコピーのアドレスをライブラリ関数への引数 `stream` として移植して使用することはできません。

## <a name="see-also"></a>関連項目

[ファイルとストリーム](../c-runtime-library/files-and-streams.md)
