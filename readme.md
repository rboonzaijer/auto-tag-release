# Testing

This repo only exists as a test for https://github.com/YarnSpinnerTool/VSCodeExtension

( Auto tagging a [release] commit )


```yaml
permissions:
    contents: write
```

```yaml
- name: Tag release
    if: ${{ github.event_name == 'push' && contains(github.event.head_commit.message, '[release]' ) }}
    run: |
        git tag ${{ steps.version.outputs.MajorMinorCommits }}
        git push origin ${{ steps.version.outputs.MajorMinorCommits }}
```
