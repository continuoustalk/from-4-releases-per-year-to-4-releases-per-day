```xml
<project name="My subsite" default="help">

    <target name="help" description="Phing target list">
        <exec executable="${phing.bin}"
              passthru="true">
            <arg value="-l"/>
        </exec>
    </target>

    <target name="generate-development-makefile"
            description="Generate the makefile for development modules.">
        <drushmakefile
            makeFile="${subsite.temporary.development.make}"
            coreVersion="${drupal.core.version}"
            projects="${development.modules.download}"
            defaultProjectDir="${development.modules.location}"
        />
    </target>

    <target name="provision-stack"
            description="Provision a stack on AWS"
            depends="setup-aws, run-stack, setup-deployment-group" />

</project>
```
