name: Create Release(s)

on:
  workflow_dispatch:
    inputs:
      version_parameters:
        description: 'Parameters to pass to "melos version"'
        required: true
        default: ' '
        type: choice
        options:
          - '--'
          - '--prerelease'
          - '--graduate'

fgh7657uhbjgmhgf
gbjnfhgmngcmvc
          fetch-depth: 0
      - name: Setup git
        run: |
          git config user.name "Ilya Virnik"
          git config user.email "ilya.virnik@gmail.com"
      - uses: subosito/flutter-action@v2
      - uses: bluefireteam/melos-action@v2
        with:
          melos-version: '3.1.0'

      - name: Create the new version(s)
        run: melos version --yes ${{ inputs.version_parameters }}

      - name: Push created version commit
        run: git push
      - name: Push modified tags
        run: git push --tags# fuei
32
