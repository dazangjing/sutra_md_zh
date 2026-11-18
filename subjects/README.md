## 三、校验

生成后须校验全部链接可达：

```bash
python3 main.py md subjects check          # 检查全部专题文件
```

## 四、检索工具

```bash
python3 main.py md subjects search 念佛            # 标题包含全部关键词
python3 main.py md subjects search --exact 妙法莲华经   # 精确匹配（去括注、去标点）
```

## 五、索引

```bash
python3 main.py md subjects index          # 重建 索引.md
```

## 六、禅宗之附录

禅宗专题之附录为《禅宗全书》目录，来源档为阅读版根下之 `禅宗全书目录.md`
（纯文本，内含「■ 《禅宗全书》目录」标记）。重建禅宗专题时，附录之条目会
自动与 `sutra_md/` 中之典籍对映成链接：

```bash
python3 main.py md subjects build              # 重建禅宗专题（自动链接化）
python3 main.py md appendix --dry-run          # 只演算，不写盘
python3 main.py md appendix --list-missing     # 列出未收本库之条目
```

未收本库者保留为纯文本——多为版本标目（「曹溪原本」「明版南藏本」）、
目录子目（「总目」「索引」）或本库未收之书（如「祖灯大统」）。

专题工具已并入 `sutra_lib_tool`（工具项目），统一入口 `main.py`，
属其 `md` 子命令组之 `subjects` 子命令（子命令 `build`／`index`／`check`／`search`），
另有 `appendix` 子命令专司附录之链接化。
